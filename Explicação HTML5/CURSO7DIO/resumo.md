# Recursos Especiais

Alguns recursos extras com relação à acessibilidade, estrutura e multimídia.

***

## ```<datalist>```

Funciona igual a tag **select**, só que vamos precisar de um **input** do tipo **search**. Esse **input** possuirá um atributo chamado **list** que será um **id** passado na tag **datalist**, exemplo:
```
<input type="search" list="options">
<datalist id="options">
    <option value="option1">option1</option>
    <option value="option2">option2</option>
    <option value="option3">option3</option>
    <option value="option4">option4</option>
</datalist>
```

Ele renderiza um pouco diferente dependendo de navegador para navegador.,
***

## ```<code>, <kbd>, <pre>```

* **kbd**: Essa tag é para colocar teclas de teclado dentro dela. Cada tecla, deve ser colocada dentro de kbd diferente:

```
<kbd>CTRL</kbd>+<kbd>C</kbd>
```
* **code**: Formato igual à **kbd**, em letra monospace, porém, essa foi feita para colar código fonte dentro dela, exemplo, se você estivesse explicando como determinada linguagem funciona e mostrasse o código de exemplo. Neste caso, use o **code**. Geralmente, nosso código é um CSS.

* **pre**: Nós usamos essa tag em caso do nosso código ter mais de uma linha. Pode combinar com code também, sendo code filha de pre.

```
<pre>
    core {
        background-color: red;
        cursor: pointer;
    }
    
</pre>
```
***

## ```<details>, <summary>```

* **details**: Essa tag é usada para detalhes. Ele cria um botão que esconde a informação digitada dentro da tag. Na frente desse botão, vem escrito *Saiba Mais* por padrão.

TESTE:
```
<details>
    <p>Esse texto está escondido.</p>
</details>
```
* **summary**: Ela é usada em conjunto com details. Serve para trocar o texto *Saiba Mais* que vem por padrão com a tag **details**.

TESTE:
```
<details>
    <summary>Como trocar o botão Saiba Mais</summary>
    <p>Esse texto está escondido.</p>
</details>
```

***

## ```<meter>, <progress>```


* **progress**: Essa tag serve para mostrar um ícone de progresso de ação no seu navegador. Ela pode ter três valores:
   * **max**: O máximo valor dela.
   * **min**: O mínimo valor dela.
   * **value**: E o valor onde ela vai iniciar. Você pode alterar isso via JavaScript.
```
<progress id="progresso" max="100" min="0" value="10"></progress>
```
* **meter**: Funciona igual ao progress. A diferença aqui é a semântica. O meter funciona mais como medidor, por exemplo de memória, enquanto progress serve para mostrar o progresso de ações.
```
<meter id="medidor" max="100" min="0" value="10"></meter>
```

***

## ```<mark>``` JavaScript

Como já mencionado essa tag serve como marca-texto. Deixa o seu texto grifado em amarelo por padrão.

Nós podemos manipular essa tag dinamicamente através do JavaScript, mas isso, é através do JavaScript.
***

## ```<canvas>```
 
* **canvas**: Serve para fazer manipulação de games dentro dessa tag. Você manipula isso através do JavaScript.
***

## Novos atributos bem úteis no HTML5

Veremos os novos ATRIBUTOS do HTML5.

* **autofocus**: Faça com que o cursor de escrita esteja na tag que este atributo foi definido.

* **placeholder**: Permite que um texto apagado seja impresso dentro das tags input.

* **required**: Muito utilizado em tags input. Faz com que os campos onde ela é definida sejam obrigatórios.

* **disabled**: Utilizado em vários situações, como tags input, fieldset, desabilita o campo no qual ela é informada.

* **maxlength**: Usado no textarea para delimitar a quantidade máxima de caracteres. ELE É EXCLUSIVO DA TAG **TEXTAREA**

* **minlength**: Usado no textarea para delimitar a quantidade mínima de caracteres.  ELE PODE SER USADO NAS TAGS **INPUT** E **TEXTAREA**

* **form**: Esse atributo permite que eu inclua tags que estão fora do nosso formulário dentro dele. Basta que eu defina um id na tag form e o informe o seu valor nas tags em que eu quiser através do atributo **form**.

* **contenteditable**: Faz com que as tags na quais este atributo foi informado fiquem disponíveis pro usuário editar diretamento no DOM do navegador. Muito útil num site de criar site.