# PTags HTML 5
HTML é **a linguagem de marcação(markup language) padrão para ser exibido em web browser.**

Criado por Tim Berners-lee
HTML 1 - 1991
HTML 2 – 1995
HTML 3 – 1997
HTML 4 – 1997
HTML 5 – 2014

### anatomia de uma tag HTML

![image-20201210150814807](image_html-css\image-20201210150814807.png)

## Semântica
Como organizar os elementos 

### Antes da versão do HTML 5

Era usado a tag <div>  para  separar o conteúdo. O que forçava o uso excessivo de classes, que tornava o código confuso e bagunçado. 

<img src="image_html-css\image-20201210140058017.png" alt="image-20201210140058017" style="zoom:80%;" />

### Na versão HTML 5

 	Foi adicionado essa versão as tags:
```
<section>seção , <aside>,<header> cabeçalho, <article> artigo, <footer>rodapé,<h1>..<h6> seções de texto
```

![](image_html-css\image-20201210141017188.png)

### Comentários no código HTML

```html
<!-- meu comentário em HTML -->
<!-- o comentários 
pode 
ocupar várias

linhas -->
<!-- <p> dentro as  tags não funcionam --> 
<p> mas fora funciona <p>

```

## Tags básicas para manipular texto 

- Para uma **paragrafo** se usa o  `<p> </p>` 

- Para um **link**  se usa a tag `<a href="https://www.google.com"> isso é um link para o google </a>` >> <a href="https://www.google.com"> isso é um link para o google </a>

  - onde o **atributo _href_** é o link para aonde o link está apontando 

    - Ele pode ser **para uma Url** mas com o "http:" na frente para indicar um link na web.
    - Ou para um **e-mail**: onde se usa na frente *"mailto:"*  seguido pelo e-mail :

    ```html
    <a href="malito:alexdejesusteroltii@gmail.com">E-mail</a>
    ```

    - pode se fazer o mesmo com **números de celular** usando "tell"

  - O **atributo _target_**  indica como o link deve ser aberto

    - usando _blank o link é aberto em outra aba do navegador:

    ```html
    <a target="_blanck">Abrir link em outra aba</a>
    ```

- **Tag de Imagem** `<img>` :

  - **O atributo src** indica a fonte da imagem, onde ela está armazenada:

    ```html
    <img src="img/imagem1.jpg"></img>
    ```

  - O **atributo alt** tem um descrição da imagem que é usada para acessibilidade e a descrição e exibida quando a a imagem não é carregada 

- Tags para **listas**:

  - `<ul>`para lista não ordenada  

  - `<ol>`para lista ordenada(com valores numéricos)

  - `<li>` é um elemento da lista 

    ```html
    <ul>
      <li>
      	elemento 1
      </li>
      <li>
      	elemento 2
      </li>
    </ul>
    <ol>
      <li>
      	elemento 1
      </li>
      <li>
      	elemento 2
      </li>
     </ol>
    ```

  ![image-20201210150447185](image_html-css\image-20201210150447185.png)

# CSS3

​	CSS é **uma linguagem de estilo de página (style sheet language )** usada para descrever a apresentação de documentos escritos em linguagem de marcação (markup language) como **HTML**. Foi proposto pela primeira vez em 1994 por **Håkon Wium Lie** que na época estava trabalhando com Tim Berners-Lee (Criador do HTML) no CERN. Mas **Bert Bos** foi influente na criação e é considerado co-criador

### Seletores:

​	O elemento **CSS edita o estilo** de um elemento HTML:

![image-20201210165716607](image_html-css\image-20201210165716607.png)

### adicionar um arquivo CSS na página HTML

```HTML
<link rel="stylesheet" href="arquivo.css"/>
```

Usando a tag `<link>`  com  o argumento `rel="stylesheet"` e o argumento `href` com o nome do arquivo css. 

### Comentários no código CSS

```css
/* um comentário */
/* ele pode ocupar 
mais de uma linha, mas
deve estar dentro da barra e os asteriscos */
```

### ID x Classes 

​	São formas de indicar que **um conjunto de elementos especifico tem estilo próprio.** São indicados em atributos no elemento HTML: 

```html
<header id="header" class="header"></header>
<header class="header"></header>
```

A **diferença** é que **ID só pode ser usado para um elemento** na pagina, ID de identificação única.

Para indicar, no CSS, a edição de estilo de uma classe e de um ID:

- **Classe**: Se usa uma hashtag(#)

  ```css
  .header {
      padding: 15px;
  }
  ```

- **ID**: se usa um ponto na frente do nome 

  ```css
  #header {
      padding: 10px;
  }
  ```

  

## Box Model

<img src="image_html-css\image-20201210172618064.png" alt="image-20201210172618064" style="zoom:60%;" />

Todo elemento HTML pode ser considerado uma caixa (box), até as tags `div`, `p`, `a`. Cada box tem cinco dimensões modificáveis:

- **content**: Conteúdo real da caixa ( do texto, da imagem, etc.). Onde os atributos **height** (altura) e **width** (largura) definem a dimensão do content 
- **padding**: Define o espaço(a distância em volta) **entre o content  e a borda (border)** 
- **border**: borda, **qualquer tipo de linha** em torno da caixa. 
- **margin**: É a distância em volta da borda, é a distancia entre as outras bordas 

Então a dimensão total de uma caixa específica é a soma das dimensões. Por exemplo, a caixa de todos os  elementos dessa classe é de _260 comprimento x 160 de altura_:

```css
.myClass {
    width: 200px ;
    height: 100px;
    padding:10px;
    border: solid 10px black;
    margin: 10px;
}
```

#### Aplicando valores diferentes no _padding_ e _margin_

- Com valor **único** para todas as direções:

```css
.coisa {
    padding: 10px;
	border: solid 1px black;
    margin: 20px; 
}
```

<img src="image_html-css\image-20201210182703045.png" alt="image-20201210182703045" style="zoom:40%;border: solid 1px black;" />

- Com valor **diferente de altura(height) e comprimento(width)**, onde o valor de **height vem primeiro**:

```css
.coisa {
    padding: 10px 5px;
	border: solid 1px black;
    margin: 20px 15px; 
}
```

<img src="image_html-css\image-20201210182956250.png" alt="image-20201210182956250" style="zoom:40%;border: solid 1px black;" />

- Com valor **diferente para todas as direções**, que são separadas, seguindo a ordem: **top(topo), right(direita), bottom(baixo) e left(esquerda)**:

```css
.coisa {
    padding: 15px 10px 5px 0px;
	border: solid 1px black;
    margin: 30px 25px 20px 15px ; 
}
```

<img src="image_html-css\image-20201210183357252.png" alt="image-20201210183357252"  style="zoom:40%;border: solid 1px black;"  />

- Determinar cada valor **separadamente** :

```css
.coisa {
    border: solid 1px black;
    padding-top: 15px;
    padding-right: 10px;
    padding-bottom: 5px;
    padding-left: 0px;
}
```

<img src="image_html-css\image-20201210184123225.png" alt="image-20201210184123225"  style="zoom:40%;border: solid 1px black;"  />

### Usando a propriedade _background_

- Escolhendo a cor de fundo:

```css 
.coisa {
    background-color: green;
    /* pode usar apenas */
    background: green;
}
```



## Propriedades da borda (border)

A borda podemos configurar no elemento CSS o **largura, o estilo** (sólida, pontilhada, tracejada) e a **cor**, sessa ordem.  Também podemos configurar cada lado separadamente:  

```css
.coisa {
    border: 3px solid blue;
    border-top: 2px dotted green; /*pontilhada*/
    border-right: 4px dashed pink;/*tracejada*/
}
```

Resultado: ![image-20201210194707550](image_html-css\image-20201210194707550.png)

Pode usar-se parâmetros para cada propriedade da borda:

```css
.coisa {
    border: 3px solid #505050;
}
/* é equivalente à */ 
.coisa {
    border-width: 3px;
    border-color: #505050;
    border-style: solid;
}
```

 Podemos ainda escolher o parâmetro de um lado da borda:

```css
.coisa {
    border-top-width: 3px;
    border-bottom-style: dotted;
}
```

#### border-radius

Essa declaração permite **arrendar a borda nas pontas**, podendo usar em porcentagem(de 0% até 50% ) ou por pixel(px). **Se pode usar dá mesma forma o top, right, bottom, left**. Exemplo:

```css
coisa{
    border-radius: 15px 50px 30px 5px; 
}
```

<img src="image_html-css\image-20201210200209481.png" alt="image-20201210200209481" style="zoom:50%;" />

```css
coisa{
    border-radius: 15px 50px 30px; 
}
```

<img src="image_html-css\image-20201210200241825.png" alt="image-20201210200241825" style="zoom:50%;" />

```css
coisa{
    border-radius: 15px 50px; 
}
```

<img src="image_html-css\image-20201210200241825.png" alt="image-20201210200241825" style="zoom:50%;" />

```css
coisa{
    border-radius: 15px;
}
```

<img src="image_html-css\image-20201210200435727.png" alt="image-20201210200435727" style="zoom:50%;" />

## Estilizando Textos

​	Declarações que alteram o estilo do texto.

### font-family

A tipografia da fonte usada, pode **informar mais de uma fonte**, onde se a primeira não funcionar ou não for aceita pelo navegador tenta a outra:

```css
#title {
    font-family: verdana;
}
.post_title{
    font-family: verdana, ariel;
}
```

### font-size

Altera o **tamanho da fonte**. Pode usar o unida em pixel, em porcentagem ou valores predeterminados como: ***medium, small e large.*** 

### font-style

O estilo da fonte: **normal(*normal*) ou itálico(*italic*).**

### font-weight

Define a espessura da fonte, normalmente se usa apenas duas: ***normal* e *bold*(negrito).**

### text-transform

Muda se está em caixa alta ou baixa. Pode ter: **uppercase(**tudo em caixa alta), **lowercase** (tudo em caixa baixa), **capitalize**(a primeira letra de cada palavra em caixa alta); 

### Text-decoration 

Coloca linhas no texto. Pode ser: **underline**(linha em baixo do texto), **overline**(linha em cima do texto) e **line-through**(linho no meio, cortando o texto)

### text-align

O alinhamento do texto, pode ser *left, right, center, justify* e outras menos usadas.  

## Dimensão e alinhamento

### width e height

Determina a largura(width) e altura(height) de um elemento pode ser em pixel ou em porcentagem(**tamanho vária de acordo com a elemento pai** ). 

### max-width e max-height

Determina a largura(width) e altura(height) máxima de um elemento, esse valor vai ser assumir max-width/max-height enquanto cabe, **se não caber**, o elemento assume um valor menor.

### Margins: auto

para ter alinhamento automático horizontalmente, fazendo os elementos caberem da melhor forma possível na tela;

