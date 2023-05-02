# Estruturando seu HTML + Formatações

## Formatando textos: ```<strong>, <i>, <b>, <u>, <mark>, <sup>, <sub>, <blockquote>```

*   ````<i>````(Itálico): É usado para gírias, frases, expressões regionais.

*   ````<b>````(Negrito): Faz com que seu conteúdo fique em negrito sem mudanças semânticas.

*   ````<strong>````(Negrito):  Faz o mesmo que a tag b, mas semanticamente, **strong** bota mais ênfase nas palavras.

*   ````<u>````(Sublinhado):  Faz com que seu conteúdo fique sublinhado.

*   ````<mark>````(Marca-texto):  Faz com que seu conteúdo fique grifado em amarelo como um marca-texto.

*   ````<sup>````(Texto elevado):  Faz com que seu conteúdo fique elevado da altura da linha como se fosse um expoente de uma potência.

*   ````<sub>````(Texto rebaixado):  Faz com que seu conteúdo fique rebaixado da altura da linha.

*   ````<blockquote>````(Citações/explicações): Ideal para colocar conteúdo de explicação ou citação de autores. Ela cria uma margem à sua esquerda.
block quote : citações ou explicações.cria um espaçamento do lado esquerdo 

**Semântica em desenvolvimento web**: Significa criar um código HTML que ao bater o olho, você sabe o significado. 
 
***

## Formatando textos: ```<font>```

````<font>````: Permite trocar a fonte do texto embora o mais indicado seja fazer isso pelo css. 

Essa TAG não faz nada sem seus atributos como: **color**, **face**(a fonte a usar). Podemos ter fontes serifadas, indicadas para leitura, ou não serifadas. 

Lembre-se de colocar mais de uma opção de fonte, separadas por vírgulas, porque o navegador renderiza a fonte que você tem, caso o usuário não a tenha, o navegador não renderiza, por isso a importância de adicionar mais opções.

Se o nome da fonte conter espaços, você deve colocá-lo e três as aspas que sejAm diferentes das usadas no atributo.

***

## Tag: ```<div>``` e ```<span>```

Vamos aprender agora a estruturar o nosso HTML. Não adiante querer sair jogando TAG aleatória e achar que o CSS vai fazer milagre! 

Digo isso, porque as duas tags, div e span, servem para isso. Elas não carregam valor semântico. Servem apenas para estruturação.

*   ```<div>```: Ela serve para estruturação do seu HTML. Lembre-se de sempre começar a estruturar o seu HTML de fora para dentro. O ideal é que você pense na estrutura do seu HTML como retângulos. Para cada um desses retângulos, crie um tag **div** específica.

*   ```<span>```: Funcionamente semelhante a ***div***, ou seja, ela não tem valor semântico e serve para estruturação, com uma diferença, ela não ocupa a horizontal do seu site por inteiro, *display: inline*.
***
## Tag: ```<fieldsets>```

Vamos usar o seguinte código como base:
```
<!DOCTYPE html>
<html lang="pt-br">
    <head>
        <meta charset="UTF-8">
        <meta http-equiv="X-UA-Compatible" content="IE=edge">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <title>Formulário simples</title>
        <style>
            .row{
                margin: 5px;
            }
            label {
                width: 100px;
                text-align: right;
                display: inline-block;
                padding-right: 5px;
            }
        </style>
    </head>
    <body>
        <h1>Formulário de Cadastro</h1>
        <form method="post">
            <div class="row">
                <label>Nome:</label><input type="text">
                <label>Email:</label><input type="text">
            </div>
            <div class="row">
                <label>Profissão:</label><input type="text">
                <label>Empresa:</label><input type="text">
            </div>
            <div class="row">
                <label>Endereço:</label><input type="text">
                <label>Número:</label><input type="text">
            </div>
            <div class="row">
                <label>Bairro:</label><input type="text">
             </div>
            <div class="row">
                <label>Cidade/UF:</label><input type="text">
            </div>
            <div class="row">
                <label>Celular:</label><input type="text">
                <label>Whatsapp:</label><input type="text">
            </div>
            
            <div class="row">
                <label>LinkedIn:</label><input type="text">
                <label>GitHub:</label><input type="text">
            </div>
            <button type="reset">Limpar</button>
            <button type="submit">Enviar Formulário</button>
        </form>
    </body>
</html>
```

Qual que é o uso da tag **fieldset**? Bom, imagine que você tenha um formulário muito grande, como no exemplo acima. E você quer segmentar esse formulário em diferentes partes, exemplo: Dados pessoais, endereço, formação acadêmica. Para cada um deles usaríamos um fieldset. É uma tag mais visual.

Vamos ver um exemplo. Vamos colocar as primeiras duas tags **div** dentro de um fieldset. Assim:
```
<fieldset>
    <div class="row">
        <label>Nome:</label><input type="text">
        <label>Email:</label><input type="text">
    </div>
    <div class="row">
        <label>Profissão:</label><input type="text">
        <label>Empresa:</label><input type="text">
    </div>
</fieldset>
```

Você verá que será criado uma borda quadrada ao redor dos elementos, o que não é muito útil. Por isso, existe uma tag filha dela chamada **legend**. O legend permite que você coloque um nome para esse campo **fieldset**.

```
<fieldset>
    <legend>Dados Pessoais</legend>
    <div class="row">
        <label>Nome:</label><input type="text">
        <label>Email:</label><input type="text">
    </div>
    <div class="row">
        <label>Profissão:</label><input type="text">
        <label>Empresa:</label><input type="text">
    </div>
</fieldset>
```

Vamos definir um espaço com campos para endereço também:
```
<fieldset>
    <legend>Endereço</legend>
    <div class="row">
        <label>Endereço:</label><input type="text">
        <label>Número:</label><input type="text">
    </div>
    <div class="row">
        <label>Bairro:</label><input type="text">
    </div>
    <div class="row">
        <label>Cidade/UF:</label><input type="text">
    </div>
</fieldset>
```

E outro para contato:

```
<fieldset>
    <legend>Contato</legend>
    <div class="row">
        <label>Celular:</label><input type="text">
        <label>Whatsapp:</label><input type="text">
    </div>
    <div class="row">
        <label>LinkedIn:</label><input type="text">
        <label>GitHub:</label><input type="text">
    </div>
</fieldset>
```
***
## Tag: ```<embeds>```

Antes de mais nada, saiba que essa tag não é mais utilizada, hoje em dia temos tags mais modernas no HTML5. Porém, entender seu funcionamento é fundamental para entendimento do resto do curso.

Antigamente, os trechos dos sites eram carregados de forma dependente. De forma que se você não conseguisse ver o início do site, também não veiria o final. Para resolver isso, eles criaram os frames. Eles carregavam de forma independente. De forma que quando você clica num trecho do site, só ele carregava.

Mais tarde, eles criaram plugins para resolver isso. De forma que você precisava usá-los para rodar arquivos no seu site. Para isso surgiu a tag **embed**, para rodar mídia externas no seu site. Ela tenha um atributo **src** para carregar os arquivos que você quer. Hoje em dia, a tag **video** substituiu o **embed** por ser mais semântica.

No caso do vídeo, você não usa o atributo src, mas a tag filha **source**.
Exemplo:

```
<video controls autoplay width="100" height="100">
    <source src="trailer.mp4"/>
</video>
```
***

## Tag: ```<iframes>```

 **Iframes** também carregam arquivos externos, permitindo que você carregue **outra página** na sua página. Ela é um a tag que abre e fecha, com o atributo **src** para mostrar a outra página. Assim como a tag **video**, você consegue ajustar a altura e largura dessa janela externa.

 Exemplo:

```
<iframe src="https://dio.me" width="500" height="500"></iframe>
```
***
## Resenha: sobre cores

![Print do resumo de como ajustar as cores.](imagem.png "Resumo de como ajustar as cores")

Quando se trata de transparência, o valor vai de  0 à 1.