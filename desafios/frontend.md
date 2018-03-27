# Desafio para Front-end

Fica a seu critério escolher que até que etapa se comprometerá a entregar.

**Observações:**

Não faça fork deste repositório

Envie o link do seu repositório, para que possamos avaliar seu código, práticas
utilizadas, testes, padrões utilizados, frameworks e bibliotecas.

Cada etapa deve ser entregue em uma TAG diferente do seu repositório.

A última etapa que fora concluída, deverá estar disponível para teste em
uma URL pública que deverá ser informada no README do projeto. 
*DICA: utilize o [Github Pages](https://help.github.com/articles/configuring-a-publishing-source-for-github-pages/)
ou [Firebase Hosting](https://firebase.google.com/docs/hosting)*.

Faça uso de práticas como: Linguagem Ubíqua, KISS, DRY e outras.

A qualidade do produto entregue e seus detalhes de apresentação contarão para
sua avaliação. Fique à vontade para adicionar mais funcionalidades ao que fora
proposto, mas não esqueça de garantir qualidade na sua solução como um todo.

## Etapa 1

### Proposta:

Implementar uma aplicação client-side onde será possível armazenar
uma lista de endereços. Deverá ser possível realizar as operações de CRUD.
Esta lista deverá ser salva no LocalStorage do navegador, e se o usuário sair
da página e voltar, a lista deverá ser recuperada do LocalStorage.

**Sugestão para a tela de cadastro:**

![Exemplo para tela de cadastro de endereço](https://raw.githubusercontent.com/estantevirtual/vagas/master/desafios/assets/exemplo_cadastro_endereco.gif)

### APIs Sugeridas

* [ViaCep](https://viacep.com.br)

### Frameworks recomendados

* [Vuejs](https://vuejs.org/)
* [Vue Cli](https://github.com/vuejs/vue-cli)
* [Bootstrap 4](https://getbootstrap.com)
* [Vue Webpack](https://github.com/vuejs-templates/webpack)



## Etapa 2

A partir do que foi proposto acima, agora faça:

### Proposta

Para cada endereço deverá ser possível visualizar:
1. a distância (em linha reta) da [localização atual do usuário](https://www.w3schools.com/html/html5_geolocation.asp)
2. clima no endereço
3. um link que abrirá um mapa com a rota para o endereço.

### APIs Sugeridas

* [LocationIQ](https://locationiq.org)
* [MetaWeather](https://www.metaweather.com)
* [GoogleMaps Urls](https://developers.google.com/maps/documentation/urls/guide)

### Frameworks recomendados

* [FontAwesome](https://fontawesome.com/)
* [Weather Icons](https://github.com/erikflowers/weather-icons)



## Etapa 3

A partir do que foi proposto acima, agora faça:

### Proposta

1. Altere variáveis do `sass` do **Bootstrap4** sem alterar seu código original
para que o site não pareça um site feito com Bootstrap4. Faça modificações ao seu
gosto.
2. Armazene a lista de endereços utilizando o Firebase.
3. Crie uma URL para que seja possível compartilhar a lista sem autenticação.
4. Garanta que apenas o dono da lista possa alterar a lista.

### APIs Sugeridas

* [Firebase](https://firebase.google.com/)

### Frameworks recomendados

* [Vuex](https://vuex.vuejs.org/en/)
* [VueFire](https://github.com/vuejs/vuefire)
* [VuexFire](https://github.com/posva/vuexfire)
