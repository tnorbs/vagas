# Desafio para Mobile

Fica a seu critério escolher que até que etapa se comprometerá a entregar.

**Observações:**

Não faça fork deste repositório

Envie o link do seu repositório, para que possamos avaliar seu código, práticas
utilizadas, testes, padrões utilizados, frameworks e bibliotecas.

Escreve um **README** instruindo como montar o ambiente para rodar seu projeto e
compilar seu aplicativo.

Cada etapa deve ser entregue em uma TAG diferente do seu repositório.

Faça uso de práticas como: Linguagem Ubíqua, KISS, DRY e outras.

A qualidade do produto entregue e seus detalhes de apresentação contarão para
sua avaliação. Fique à vontade para adicionar mais funcionalidades ao que fora
proposto, mas não esqueça de garantir qualidade na sua solução como um todo.

## Etapa 1

### Proposta:

Implementar um APP para facilitar o cadastro de livros de uma loja para controlar seu 
estoque.

### Funcionalidades:

* Lista de livros já cadastrados.
* Cadastrar mais livros
  * Usando a câmera com leitor de código de barra (**Obrigatório**)
  * Usando campo de digitação de números do ISBN (failover)
* Obter dados do livro em uma API usando o ISBN
* Solicitar o valor e quantidade em estoque do livro cadastrado
* Permitir alterar informações do livro

### APIs Sugeridas

* [ISBNdb.com]('https://isbndb.com/')


### Frameworks indicados

* [NativeScript Vue](https://nativescript-vue.org/)


## Etapa 2A

A partir do que foi proposta na etapa 1, agora faça:


### Proposta

* Permitir adicionar varias fotos de um livro
* Permitir o **crop** da capa de um livro


## Etapa 2B

A partir do que foi proposto na etapa 1, agora faça:


### Proposta

1. Permitir login social utilizando Firebase
2. Armazenar os livros cadastrados em um dos bancos do Firebase
3. Armazenar fotos no Firebase Storage (caso tenha feito a Etapa 2A)
4. Permitir o sync realtime entre dispositivos logados com a mesma conta


### APIs Sugeridas

* [Firebase](https://firebase.google.com/)


### Frameworks recomendados

* [VueFire](https://github.com/vuejs/vuefire)


