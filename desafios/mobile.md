# Desafio para Mobile

Fica a seu critério escolher que até que etapa se comprometerá a entregar.

**Observações:**

Não faça fork deste repositório. Envie o link do seu repositório, para que
possamos avaliar seu código, práticas utilizadas, testes, padrões utilizados,
frameworks e bibliotecas.

Escreve um **README** instruindo como montar o ambiente para rodar seu
aplicativo. Se você escrever testes, nos diga também como
rodá-los. Se você usar algum tipo de framework de geração de código,
nos diga como usá-lo.

Apesar de ser um projeto bem pequeno, faça uso das melhores práticas de
programação que souber. Sinta-se encorajado a escrever testes :)

Cada etapa deve ser entregue em uma TAG diferente do seu repositório.

A qualidade do produto entregue e seus detalhes de apresentação contarão para
sua avaliação. Fique à vontade para adicionar mais funcionalidades ao que fora
proposto, mas não esqueça de garantir qualidade na sua solução como um todo.

Lembre de fazer a UI do seu projeto de acordo com os padrões da plataforma
para qual está desenvolvendo.

Você pode fazer o desafio usando Kotlin, Swift ou React-native. Se
React-native for escolhido, nós iremos testar o aplicativo tanto no android
como no iOS. Caso usa Kotlin ou Swift, ele será testado apenas na sua
plataforma específica (obviamente).

## Etapa 1

### Proposta:

Implementar um app nativo que lista linguagens de programação.

### Funcionalidades:

* Lista de linguagens de programação, disponível em: *https://cultura-languages.herokuapp.com/languages?page=1*
Na lista, exibir apenas a imagem e o nome da linguagem.
* Ao clicar numa linguagem da lista, ir para tela de detalhes dela, onde todos os campos serão exibidos.

## Etapa 2 (opcional)

A partir do que foi proposta na etapa 1, agora faça:


### Proposta

* Permitir que o usuário "favorite" uma linguagem. Salve essa lista de favoritos localmente.


## Etapa 3 (opcional)

A partir do que foi proposto na etapa 2, agora faça:


### Proposta

* Salvar a lista de favoritos no [Firebase](https://firebase.google.com/), no modo anônimo.
Pode ser usado outro backend, caso não queira usar o firebase.

## Etapa Coringa (opcional)

Essa etapa pode ser feita independente das outras etapas opcionais
A partir do que foi proposto em qualquer etapa, agora faça:


### Proposta

* Dar a possibilidade pro usuário compartilhar uma linguagem. (compartilhar por email, Facebook, Twitter, etc)
* Deeplink pra lista de linguagens.
* Deeplink para tela de detalhes de uma linguagem. A URL para pegar os dados de uma linguagem específica é: https://cultura-languages.herokuapp.com/languages/1
