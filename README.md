# On5-responsivo

Turma Online 5 | Front-end | 2020 | Semana 2 | Responsivo

## Layout Responsivo:

1 [O que é Mobile First](#mobileFirst)

2 [Adaptativo e Responsivo](#layoutResponsivo)

3 [Resolução de tela x tamanho de tela](#resolucaoTamanho)

4 [Meta tag viewport](#viewportMetaTag)

5 [Media Queries e Breakpoints](#breakpointsMedia)

6 [Unidades de Medidas em Responsividade](#unidadesMedida)

7 [Display: flex](#displays)

8 [Cross-browser testing](#crossBrowser)

**[Exercício - Entrega 12/06](#exercicio)**

---

<div id='mobileFirst'></div>

**O QUE É MOBILE FIRST:**

---

Quando construimos o nosso projeto para que seja prioritariamente visualizado em formato mobile. Assim a contrução do nosso CSS parte de configuraçao e funcionalidade que serão usados em devices menores, como um celular, por exemplo.

**Por que é importante?**

O celulares ou tablets, aparelhos cada vez mais portáteis, são os principais meios de acesso à internet. Logo, desenvolvermos sites priorizando a performance nesses aparelhos é muito importante para um negócio\produto.

Mas é bem importante trabalhar bem o CSS de modo a não deixar perder funcionalidades em telas maiores.

Ex: Nosso ponto de partida é uma tela 768px. Ao invés de mudar os estilos à medida que a largura fica menor que 768px, nós devemos mudar o estilo da página à medida que a largura fica maior que 768px. Isso faz o nosso projeto Mobile First!

![mobile-desktop](https://urucumdigital.com/wp-content/uploads/2019/08/3038367-slide-s-8-9-gifs-that-explain-responsive-design-brilliantly-08desktop-first-vs-mobile-first-3.gif)

---

<div id='layoutResponsivo'></div>

**ADAPTATIVO E RESPONSIVO:**

---

O conceito de _layout responsivo_ surgiu em 2010, com o designer Ethan Marcotte
(https://alistapart.com/d/responsive-web-design/ex/ex-site-flexible.html https://alistapart.com/article/responsive-web-design) como uma forma de facilitar a adaptação de telas aos mais diversos tipos de tamanhos que começaram a surgir no mercado.

- **Responsivo** e **Adaptativo** são praticamente a mesma coisa em se tratando de mudar a aparência/funcionalidade do site em diferentes tamanhos de telas - mais especificamente na largura (width)

  **Diferenças de termos:**

  - **Responsivo**: ele 'responde' ao tamanho do browser, independente de marcação pontos específicos onde os tamanhos mudam, adaptando todo o conteúdo e funcionalidades.

  - **Adaptativo**: o conteúdo se molda em determinados pontos de mudanças de tamanho da tela. Estes pontos (breakpoints) são especificados no CSS, indicando qual conteúdo e como ele se modifica exatamente a partir desses pontos.

  **Pontos positivos Adaptativo:**

  - UX friendly: mantém o mesmo design adaptado para diferentes formatos de tela, sempre pensando na melhor usabilidade para cada formato;
  - É mais barato desenvolver um site responsivo do que ter que desenvolver versões diferentes do site, como uma versão mobile, por exemplo;
  - É mais fácil dar manutenção, porque o código está todo em um lugar só (se tivesse uma versão mobile e um app, por exemplo, uma mudança de código teria que ser feita em três lugares);
  - SEO friendly: como a aplicação só tem uma URL isso ajuda a manter todos os dados consistentes e a melhorar a posição no ranking do Google.

  **Pontos negativos Adaptativo:**

  - Normalmente os desenvolvedores testam o site nas principais resoluções/dispositivos disponíveis no mercado, porém é possível que em alguns dispositivos com formato de tela/resoluções não tão comuns o site não renderize conforme o esperado;
  - Versões antigas do IE;
  - Se o layout e a arquitetura do código não forem desenhadas antes de começar o trabalho, o site pode ficar muito difícil de manter/modificar;
  - O site responsivo pode ser mais demorado para carregar (se tiver muitas imagens redimensionadas, se tiver muitas chamadas externas de scripts, etc.).

---

  <div id='resolucaoTamanho'></div>

**RESOLUÇÃO DE TELA x TAMANHO DE TELA:**

---

- Resolução de tela: A resolução da tela de um dispositivo é o número de pixels em cada dimensão que podem ser exibidos.

- Tamanho de tela: tamanho físico da tela, normalmente medido em polegadas

A resolução de monitores de dispositivos digitais indica o número de pontos (ou pixels) que compõem a imagem que aparece na tela. Uma tela com 1920 x 1080 mostra 1920 pontos em cada uma das 1080 linhas do monitor!

Dispositivos com o mesmo tamanho podem ter resoluções de tela diferentes!

---

<div id='viewportMetaTag'></div>

**VIEWPORT META TAG:**

---

Quando se trata de responsividade temos que usar a metatag de nome VIEWPORT, da seguinte maneira:

```
 <head>
   <meta charset="utf-8">
   <meta name="viewport" content="width=device-width, initial-scale=1">
   <link href="css/style.css" rel="stylesheet">
 </head>
```

Esta tag diz ao browser para renderizar o conteúdo do site de acordo com os diferentes tamanhos dos dispositivos

---

<div id='breakpointsMedia'></div>

**MEDIA QUERIES:**

---

A partir de **breakpoints**, ou seja, tamanho de telas especificados pelo desenvolvedor, tem-se a variação do site de modo que todo o conteúdo/funcionalidades fique bem adaptados nessa telas.

No CSS, é onde são especificados esses breakpoints, e isso é pensado de acordo com as necessidades dos sites (público, negócio, etc)

Com as media queries e os breakpoints vamos começar a adicionar um pouco de lógica no css. O que vai acontecer é que o browser vai ler a folha de estilos, e SE a condição for verdadeira, ela vai executar o bloco de código, SENÃO ele vai apenas ignorá-lo.

A propriedade width controla o tamanho da viewport. O valor desta propriedade pode ser definido com um número específico de píxels como por exemplo width=600 ou com um valor especial chamado device-width que representa a largura da onde o conteúdo está sendo apresentado em pixels de CSS considerando uma escala de 100%. (Ainda há as propriedades height e device-height, as quais podem ser úteis para páginas com elementos que mudam de posição baseado na altura da viewport.)

A propriedade initial-scale controla o nível de amplificação quando a página é carregada pela primeira vez.

- Trabalhando com 'MEDIA QUERIES':

  Se [largura do dispositivo] for menor ou igual a 768px, então execute o {...}

  ```
      @media (max-width: 768px) {
        .nome-da-classe {
          color: #fff; /* elemento que vai ser modificado/adicionado/sobrescrito nessa resolução */
        }
      }
  ```

  Se [largura do dispositivo] for maior ou igual a 768px, então execute o {...}

  ```
      @media (min-width: 768px) {
        .nome-da-classe {
          color: #fff; /* elemento que vai ser modificado/adicionado/sobrescrito nessa resolução */
        }
      }
  ```

  Se [largura do dispositivo] for entre 768px e 600px, então execute o {...}

  ```
      @media (max-width: 768px) and (min-width: 600px) {
        .nome-da-classe {
          color: #fff; /* elemento que vai ser modificado/adicionado/sobrescrito nessa resolução */
        }
      }
  ```

/_ esse é um bloco normal de css, o browser vai ler e mostrar esses valores na tela do usuário _/

```
  .box {
    border: 1px solid #000;
    width: 320px;
    height: 120px;
    background-color: red;
  }
```

/_ esse é um bloco condicional, o browser vai ler e mostrar esses valores na tela do usuário SE a resolução da tela for menor que 768px _/

```
  @media (max-width: 768px) {
    .box {
      background-color: blue;
    }
  }
```

/_ esse é um bloco condicional, o browser vai ler e mostrar esses valores na tela do usuário SE a resolução da tela for menor que 420px _/

```
  @media (max-width: 420px) {
    .box {
      width: 100%;
      background-color: yellow;
    }
  }
```

**GRID FLUIDO:**

É o uso de % ao invés de valores absolutos(px) para definir tamanhos de elementos no CSS. Essa é uma técnica que pode ser usada sempre, não apenas visando os layouts responsivos.

**Para ler:** <https://www.w3schools.com/Css/css_rwd_grid.asp>

**Importante:**
Como o termo Responsividade é um conceito já implementado, ambos os casos - Adaptativo e Responsivo - são sempre considerados RESPONSIVIDADE!

Em nossa aula vamos focar no desenvolvimento da Responsividade com Media-Queries, ou seja, com 'breakpoints' definidos.
Assim trabalharemos com os seguintes 'breakpoints':

**1280px (desktop)**

**768px (tablet - vertical)**

**420px (mobile)**

---

<div id='unidadesMedida'></div>

**UNIDADES DE MEDIDAS EM RESPONSIVIDADE:**

---

![measures](https://webandcrafts.com/blog/wp-content/uploads/2019/02/Relative-units.gif)

**Medida absoluta:**

- px: o pixel é uma medida fixa, logo absoluta. Quando aplicamos um valor para a fonte em px, dizemos ao navegador que o tamanho da nossa fonte será sempre aquele, independente de tamanho e resolução de telas.

**Medidas relativas:**

- em: Ao declararmos um valor com unidade em, dizemos que esse número é relativo ao tamanho da fonte do elemento pai.

[![em](https://user-images.githubusercontent.com/42356402/67354175-c855ab80-f52a-11e9-982c-6f8cb1cf03a2.png)](https://codepen.io/gisantin/pen/qBBrZEy)

- rem("root em"): A unidade rem é relativa ao elemento root, ou seja, o valor da fonte definida no html ou body.
  Ex: 1em = valor declarado para a fonte onde ele esteja sendo usado
  1rem = valor declarado para a fonte na raiz do projeto (html, body)

[![rem](https://user-images.githubusercontent.com/42356402/67407721-4eefa480-f58e-11e9-8854-e3210c4d4916.png)](https://codepen.io/gisantin/pen/WNNpwRG)

- vh: viewport-height é nome para vh - quando se aplica a unidade vh, temos que o valor também aplicado é de 1% do valor da altura do container onde se está trabalhando(viewport).

- vw: viewport-width é o nome para vw - quando se aplica a unidade vw, temos que o valor também aplicado é de 1% do valor da largura do container onde se está trabalhando(viewport).

**Viewport** nada mais é que a área visível de uma página web para o seu usuário, essa viewport pode variar de acordo com o dispositivo, sendo menor em celulares e maior em desktops.

---

<div id='mobileFirst'></div>

**O QUE É MOBILE FIRST:**

---

Quando construimos o nosso projeto para que seja prioritariamente visualizado em formato mobile. Assim a contrução do nosso CSS parte de configuraçao e funcionalidade que serão usados em devices menores, como um celular, por exemplo.

**Por que é importante?**

O celulares ou tablets, aparelhos cada vez mais portáteis, são os principais meios de acesso à internet. Logo, desenvolvermos sites priorizando a performance nesses aparelhos é muito importante para um negócio\produto.

Mas é bem importante trabalhar bem o CSS de modo a não deixar perder funcionalidades em telas maiores.

Ex: Nosso ponto de partida é uma tela 768px. Ao invés de mudar os estilos à medida que a largura fica menor que 768px, nós devemos mudar o estilo da página à medida que a largura fica maior que 768px. Isso faz o nosso projeto Mobile First!

![mobile-desktop](https://urucumdigital.com/wp-content/uploads/2019/08/3038367-slide-s-8-9-gifs-that-explain-responsive-design-brilliantly-08desktop-first-vs-mobile-first-3.gif)

---

<div id='displays'></div>

**DISPLAY: FLEX :**

---

A propriedade de css display: flex permite alinhar com facilidade elementos lado a lado.

Você deve adicionar a propriedade no elemento pai para alinhar o conteúdo filho lado a lado.

```
<nav class="container">
  <div>Home</div>
  <div>Busca</div>
  <div>Sair</div>
</nav>

.container {
  display: flex;
}
```

O display: flex tem propriedade complementares que permitem alinhar os elementos filhos ao centro, à direita, à esquerda, tanto na horizontal como na vertical.

**Jogo do Flexbox:** <https://flexboxfroggy.com/#pt-br>

Flexbox em gifs: <https://medium.com/@lucasjs/como-o-flexbox-funciona-explicado-com-gifs-grandes-e-coloridos-26c42a0bcdc>
Guia Flexbox: <https://css-tricks.com/snippets/css/a-guide-to-flexbox/>

---

<div id='crossBrowser'></div>

**CROSS-BROWSER TESTING:**

---

Testar seu projeto ou aplicação em diferentes navegadores (browsers) e observar se todos ou a maioria deles mantém estilo e funcionalidades originais sem comprometer sua qualidade de navegaçao/usabilidade.

**Como testar?:**

- BrowserStack
- Google insights
- What is my screen resolution
- Chrome DevTools

---

<div id='exercicio'></div>

## Exercício - Aula 12/06

---

## Etapas do projeto

1. Faça o clone do projeto e crie uma pasta com seu nome dentro da pasta exercicio-alunas
2. O html já está todo pronto, você irá criar e ajustar apenas o CSS
3. O estilo deverá ser aplicado considerando a responsividade **MOBILE FIRST** e deverá se adapatar para as versões tablet(768px/1024px) e desktop(1280px)
4. Na pasta _exercicio/orientacoes_ temos o layout finalizado versão mobile e desktop

## Orientações gerais

- Clonar este repositório: `https://github.com/reprograma/On5-responsivo`
- Crie sua branch: `git checkout -b seuNome`, ex: `git checkout -b barbaraAguilar`
- **Atenção**: Faça alterações apenas nos arquivos dentro da sua pasta, os arquivos da pasta raiz _exercicio_ não deverão ser modificados para não acarretar conflitos de git **ALTERA OS ARQUIVOS SOMENTE DENTRO DA SUA PASTA**
- Adicione uma pasta com seu-nome dentro da pasta `exercicio`, ex: _barbara-aguilar_
- Dentro da pasta com seu-nome, copie os arquivos da pasta raiz _exercicio_
- trabalhe dentro da sua branch fazendo todos os commits e pushs direcionados para ela, ao finalizar o projeto realizar o `pull request` para a master
- A organização final da pasta deverá ficar assim:

```
exercicio-alunas/
  seu-nome/
    index.html
    css/
      style.css
    img/
      antartida-1.jpg
      facebook.png
      foto-banner.jpg
      groelandia-1.jpg
      menu-hamburger.jpg
      siberia-1.jpg
      twitter.png
      youtube.png
```

---

Links para consulta:

<https://css-tricks.com/the-difference-between-responsive-and-adaptive-design/>

<https://nextecommerce.com.br/design-responsivo-ou-entrega-adaptativa-o-que-e-melhor-para-o-marketing-digital/>

<https://www.freecodecamp.org/news/how-to-make-your-html-responsive-by-adding-a-single-line-of-css-2a62de81e431/>

<https://drafts.csswg.org/css-values-3/#font-relative-lengths>

<https://tableless.com.br/manipulando-metatag-viewport/>

<https://www.w3schools.com/Css/css_rwd_mediaqueries.asp>

<https://blog.caelum.com.br/flexibilidade-em-paginas-para-dispositivos-moveis-com-media-queries/>

<https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Grid_Layout/Box_Alignment_in_CSS_Grid_Layout>

<https://www.freecodecamp.org/news/an-animated-guide-to-flexbox-d280cf6afc35/>

<https://www.softwaretestinghelp.com/how-is-cross-browser-testing-performed/>
