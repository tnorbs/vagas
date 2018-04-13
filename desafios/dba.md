# Desafio para DBA

Fica a seu critério escolher que até que etapa se comprometerá a entregar.

**Observações:**

Não faça fork deste repositório

Envie o link da sua solução (ou [Gist](https://gist.github.com/)),
para que possamos avaliar sua solução e práticas utilizadas. Se possível, inclua
links com artigos para embasar sua solução.

Nosso banco de dados é Mysql.

*Contexto geral*

Temos um cluster de Mysql, com 1 banco master e 2 slaves.
Todas as escritas são feitas no banco master e todas as leituras de dados
são feitas em um dos slaves e todos os relatórios são feitos no outro slave.

## Problema 1

### Escopo:

Todos os dias é executada uma query que gera uma tabela com os resultados da consulta. 
Hoje essa estratégia está levando aproximadamente 1h, e durante o tempo de execução da query
ocorrem alguns erros em sistema que necessitam desta tabela.


### Query

```sql
  DROP TABLE analise_historico;
  CREATE TABLE analise_historico AS SELECT
    i.produto_id,
    i.titulo,
    i.autor,
    i.editora,
    i.ano,
    AVG(IF(i.novo = FALSE, NULL, vi.preco)) AS preco_medio_novo,
    AVG(IF(i.novo = FALSE, vi.preco, NULL)) AS preco_medio_usado,
    MIN(IF(i.novo = FALSE, vi.preco, NULL)) AS preco_minimo_usado,
    MIN(IF(i.novo = FALSE, NULL, vi.preco)) AS preco_minimo_novo,
    AVG(IF(i.novo = FALSE, vi.peso, NULL))  AS peso_medio_usado,
    AVG(IF(i.novo = FALSE, NULL, vi.peso))  AS peso_medio_novo,
    MIN(IF(i.novo = FALSE, vi.peso, NULL))  AS peso_minimo_usado,
    MIN(IF(i.novo = FALSE, NULL, vi.peso))  AS peso_minimo_novo,
    COUNT(IF(i.novo = FALSE, 1, NULL))      AS qtde_usado,
    COUNT(IF(i.novo = FALSE, NULL, 1))      AS qtde_novo
  FROM item i
    LEFT JOIN venda v ON i.venda_id = v.id
  WHERE v.log >= current_date() - INTERVAL 300 DAY
  GROUP BY i.produto_id;
```


### Contexto

* Tabela **VENDA**: 100 milhões de tuplas
* Tabela **ITEM**: 5 milhões de tuplas

## Problema 2

Precisamos rodar uma query de atualização de pesos na base absoluta de livros
baseado no histórico de vendas de itens. Esta consulta percorre 3 schemas diferentes
e é executada 1x por mês. 

Quando é executada, está demorando 5 horas e realizando LOCKs nas tabelas,
impossibilitando vendas durante o período que está sendo executada.

### Update

```sql
UPDATE absoluto.livros l INNER JOIN (
  SELECT
    m.isbn,
    round(avg(c.peso)) peso
  FROM vitrine.mapa m  
    JOIN vitrine.livro v ON m.livro_id = v.id
    JOIN checkout.itens c ON v.livro_id = c.livro_id
    JOIN checkout.carrinho cr on cr.id = c.carrinho_id 
  WHERE
     cr.log >= now() - INTERVAL 30 DAY
  GROUP BY 1
  ) as s on s.isbn = p.isnb
SET l.peso = s.peso
```

### Contexto

* Tabela **CARRINHO**: 50 milhões de tuplas
* Tabela **ITENS**: 500 milhões de tuplas
* Tabela **VITRINE**: 10 milhões de tuplas
* Tabela **ABSOLUTA**: 8 milhões de tuplas


## Problema 3

Com a evolução constante em nossos sistemas e regras de negócio,
eventualmente precisamos adicionar novas colunas em tabelas extremamente grandes
em nosso banco de dados. Quais estratégias podemos executar para ter o mínimo ou 0
de downtime em nossa aplicação?
