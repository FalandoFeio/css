# Flexbox

## display: Flex

Determina que dentro do container iremos utilizar propriedades flex-box.

### display: inline-flex

Indica que iremos posicionar os nossos elementos utilizando flex-box mas serão manipulados em linha

### flex-direction

> valor-default: row

Determina o qual o eixo principal de um container. Por padrão o eixo principal do container é o eixo horizontal (ROW).

O container é um elemento HTML que "abraça" os outros por exemplo uma div, ou seja, o flex-box seria utilizado para posicionar os elementos dentro desta div pois ele altera o eixo apenas do container e não de toda página.

Column:

Quando setamos esta propriedade, estamos dizendo que o eixo principal do nosso container é o heixo transversal, por isso, começamos a colocar os elementos um em baixo do outro. Por exemplo: um menu hamburguer lateral

Row:

No caso do Row, setamos o eixo principal do container para o eixo horizontal, ou seja, os itens ficarão uns ao lado os outros. Por exemplo uma nav bar na horizontal.

No caso dos "inverse" (row-inverse, column-inverse), o flex- box inverte o eixo principal, então o que está me primeiro vira último do lado oposto do container.

Exemplo:

Imagine um menu lateral, do lado esquero da página com os seguintes valores e nesta ordem: `Home, About, Contact` . 

Agora vamos adicionar a propriedade do flex-box row-inverse:

Os elementos irão parar do outro lado da página na ordem:

 `Contact, About, Home`

* Existem outros valores, mas acredito que não sejam tão relevantes para um resumão *

### justify-content

> valor default: flex-start

Alinha os elementos do container de acordo com a direção que o conteúdo está fluindo (flex-direction) sem alterar o tamanho dos elementos dentro do container.

Temos algumas outras opções, como por exemplo:

flex-end: joga para o final do container

flex-start (padrão): inicio do container

space-between: Joga o primeiro filho para o inicio e o ultimo para o final

space-around: Divide os elementos em espaços iguais, com exceção do espaço entre o primeiro elemento e a borda superior do container e o ultimo elemento e a borda inferior onde o espaço será a metade dos demais.

### flex

A propriedade flex junto com a propriedade flex-direction ROW, te ajuda a dividir a width o conteúdo pela página.

Por exemplo se todos elementos estiver com flex:1 indica que o espaço que eles ocupam deve ser dividido igualmente

## align-items

> valor-default: stretch

Por padrão quando utilizamos o flex-box os itens do container são setados para ocupar todo o espaço daquele container.

Quando setamos o valor de align-items indicamos de onde o nosso conteúdo deve começar e que ele deve acabar assim que o conteúdo acabar também

Exemplo:

Este exemplo precisará ser feito em código, difícil explicar só com palavras:

```html
<div style="display:flex; align-items: flex-start;">
    <div style="border: 2px solid; flex: 1">
        <article>
            Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the
            industry's standard
            dummy text ever since the 1500.
        </article>
    </div>
    <div style="border: 2px solid; flex: 1">
        <article>Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the
            industry's standard
            dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make
            a type specimen
            book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining
            essentially
            unchanged.
        </article>
    </div>
    <div style="border: 2px solid; flex:1">
        <article>
            Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard
            dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen
            book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially
            unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more
            recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.
        </article>
    </div>
</div>
```

### align-self

Faz exatamente a mesma coisa que o align-items, mas, apenas com o filho do container especificado.

Se quiser testar, copia o código acima e pega a primeira div e coloca dentro do style align-self: flex-end;

### Redimensionando os elementos dentro do container

Temos 3 propriedades para redimensionar conteúdo dentro do container que ficam dentro da propriedade flex vista anteriormente:

***flex-basis, flex-grow e flex-shrink.***

### flex-basis

Redimensiona o elemento de acordo com o flex-direction então se o flex-direction for row seta o valor da width, se for column do height. 

Ele sobrepõe outras propriedades que estejam no  elemento, ou seja, se o elemento tiver width 200px e setarmos neste mesmo elemento flex-basis 150px o elemento terá 150px porém respeitando o max e min width.

Se quisermos dividir o espaço de todas os filhos do container, setamos o flex-basis para 0.

### flex-grow

Determina como o espaço que está sobrando além do flex-basis no elemento deve ser utilizado. Por exemplo:

Se tivermos um width total de 200px e um flex-basis de 100px podemos fazer com que ele utilize todo o espaço setando o flex-grow em cada item de acordo com a proporção desejada.

O valor é dado em proporção, então se tivermos 3 elementos um com flex-grow 1, outro com 2 e outro com 3. O primeiro  elemento terá 1/6 do espaço, segundo 2/6 e o terceiro 3/6 no espaço sobrando.

### flex-shrink

Define qual o comportamento se o conteúdo do flex-basis ultrapassar o tamanho total permitido. O valor que o flex-shrink for setado será a quantidade de vezes que aquele elemento ocupará espaço a mais dentro do flex-basis

### flex-wrap

Faz com que os elementos do container respeitem o limite da página.

#### CSS-GRID X FLEXBOX

Utilizar o css grid quando já souber o que vai precisar colocar na tela e o flexbox quando quiser que tudo se encaixe mas for algo evolutivo.