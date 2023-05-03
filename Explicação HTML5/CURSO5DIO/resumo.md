# Como estruturar tabelas no HTML5

## Sobre Tabelas

Uma tábela é composta por 3 partes. Cédulas, colunas e linhas. 

As colunas são divisões na vertical da tabela.

As linhas são divisões na horizontal da tabela.

As cédulas é o encontro da linha com a coluna.

Quando usar tabelas? Quando você precisa apresentar dados em forma de tabela.

***

## Tag ```<table>```

Vamos o usar o seguinte código como base:

```
<!DOCTYPE html>
<html lang="pt-br">
    <head>
        <meta charset="UTF-8">
        <meta http-equiv="X-UA-Compatible" content="IE=edge">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <title>Trabalhando com Tabelas</title>
    </head>
    <body>
        
    </body>
</html>
```

Então, para criar a nossa tabela precisamos a tag **table**. Ela é uma tag que abre e fecha -  ```<table></table>``` -, por isso, você deve colocar os seus dados entre elas.

Essa tag, não funciona sozinha. Para cada nova linha que você adicionar na tabela, você deve usar uma tag **tr** - ```<tr></tr>``` - e colocar os dados daquela linha dentro.

Dentro das tags **tr**, você deve colocar uma tag **td** para cada dado daquela linha.

Dito isso, vamos fazer um exemplo:

```
<!DOCTYPE html>
<html lang="pt-br">
    <head>
        <meta charset="UTF-8">
        <meta http-equiv="X-UA-Compatible" content="IE=edge">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <title>Trabalhando com Tabelas</title>
    </head>
    <body>
        <table>
            <tr>
                <td>JavaScript</td>
                <td>FrontEnd</td>
            </tr>
            <tr>
                <td>Python</td>
                <td>BackEnd</td>
            </tr>
            <tr>
                <td>C#</td>
                <td>BackEnd</td>
            </tr>
        </table>
        
    </body>
</html>
```

Além disso, nós podemos adicionar alguns atributos na tag **table** para estilizar toda a tabela.

*   **border**: Define as bordas externas e internas da tabela. Você deve passar um valor numérico como **1**, por exemplo.

*   **width**: Define a largura da tabela.

*   **align**: Define o alinhamento da tabela na tela. Pode colocar o valor **center**, por exemplo.

*   **cellspacing**: Define o espaço entre as células de cada linha. Você deve passar um valor numérico.

*   **cellpadding**: Aumenta o espaço dentro de cada tag **td**.

*   **summary**: Nem tem utilidade para o usuário, mas leitores de tela vão verificar o conteúdo dentro desse atributo. Ele passa um resumo sobre do que a tabela se trata.

Lembre-se que todosesses atributos são passados dentro da tag **table**.

***

## Tag ```<tr>```

Como explicado,  o conteúdo de cada linha da tabela deve estar dentro de uma tag **tr**. Ela define cada linha tabela.

Nâo tem muitos atributos específicos para falar aqui. Se você quiser estilizar a tabela no formato zebra, é na tag **tr** que você vai mexer. Nesse caso, vamos usar um pouco de CSS. Vamos colocar outros detalhes também.

Adicione o seguinte código no head do seu html
```
<style>
    table tr::nth-child(even){
        background-color: burlywood;
    }
    table tr:hover td(even){
        background-color: darkgrey;
    }
</style>
```

***

## Tag ```<td>``` e ```<th>```

A tag **th** é muito simples. Ela mostra para o navegador quais células são o cabeçario da minha tabela. - ```<th></th>``` -.

Por boa prática os nomes de cabeçário devem ser curtos e fáceis de entender. Se você precisa de uma descrição maior para aquele cabeçário, passe isso através do atributo **title** que pode ser colocado dentro da tag **th**.

Exemplo: Imagine que você tem no cabeçário, uma cédula onde vai colocar o *nome dos produtos da sua loja*. Você vai colocar, como conteúdo da cédula, a palavra *Nome* apenas. Se precisar descrever isso, use o atributo **title** e insira a descrição dentro dele, um balão de texto será exibido para o usuário sempre que ele passar o mouse em cima da cédula.
Código:
```
<table>
    <tr>
        <th title="Nome dos produtos da sua loja">Nome</th>
    </tr>
</table>
```
Para os dados, nós usamos a tag **td**. - ```<td></td>``` -.


***

## Tags: ```<tbody>```, ```<thead>```, ```<tfoot>``` e ```<caption>```

Por questões de organização, nós podemos usar essas três tags. 

Vamos começar com **thead**. A tag **thead** serve para demilitarmos o espaço onde é o cabeçário da nossa tabela. Nós a colocamos antes da tag **tr** do cabeçário, exemplo:

```
<table>
    <thead>
        <tr>
            <th>Nome</th>
            <th>Sobrenome</th>
            <th>Email</th>
        </tr>
    </thead>
</table>
```

Da mesma forma, podemos usar tag **tbody** para delimitarmos o corpo da nossa tabela. Nós a colocamos antes de todas as tags **tr** dos dados da tabela, exemplo:

```
<table>
    <thead>
        <tr>
            <th>Nome</th>
            <th>Sobrenome</th>
            <th>Email</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>João</td>
            <td>Peres</td>
            <td>jojoaoao@.com</td>
        </tr>
        <tr>
            <td>Maria</td>
            <td>Souzao</td>
            <td>maririo@.com</td>
        </tr>
        <tr>
            <td>Paulo</td>
            <td>Mendes</td>
            <td>pauloo@.com</td>
        </tr>
    </tbody>
</table>
```

E, se tivermos um rodapé na tabela, podemos colocar a tag **tfoot**, exemplo:

```
<table>
    <thead>
        <tr>
            <th>Nome</th>
            <th>Sobrenome</th>
            <th>Email</th>
        </tr>
    </thead>
</table>
```

Da mesma forma, podemos usar tag **tbody** para delimitarmos o corpo da nossa tabela. Nós a colocamos antes de todas as tags **tr** dos dados da tabela, exemplo:

```
<table>
    <thead>
        <tr>
            <th>Nome</th>
            <th>Sobrenome</th>
            <th>Email</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>João</td>
            <td>Peres</td>
            <td>jojoaoao@.com</td>
        </tr>
        <tr>
            <td>Maria</td>
            <td>Souzao</td>
            <td>maririo@.com</td>
        </tr>
        <tr>
            <td>Paulo</td>
            <td>Mendes</td>
            <td>pauloo@.com</td>
        </tr>
    </tbody>
    <tfoot>
        <p>Aqui é o rodapé da nossa tabela.</p>
    </tfoot>
</table>
```

Mas qual é a vantagem dessas tags? Se você testou o código com e sem elas não viu diferença nenhuma. A diferença é que fica mais organizado e vísivel de ver onde cada parte da tabela está. Além disso, se você inverter a ordem do corpo da tabela com o cabeçário ou rodapé, a tabela vai ser exibido na ordem certa.

Exemplo: VOCÊ VERÁ QUE NADA VAI MUDAR.
```
<table>
    <tbody>
        <tr>
            <td>João</td>
            <td>Peres</td>
            <td>jojoaoao@.com</td>
        </tr>
        <tr>
            <td>Maria</td>
            <td>Souzao</td>
            <td>maririo@.com</td>
        </tr>
        <tr>
            <td>Paulo</td>
            <td>Mendes</td>
            <td>pauloo@.com</td>
        </tr>
    </tbody>
    <tfoot>
        <p>Aqui é o rodapé da nossa tabela.</p>
    </tfoot>
    <thead>
        <tr>
            <th>Nome</th>
            <th>Sobrenome</th>
            <th>Email</th>
        </tr>
    </thead>
</table>
```

No caso, de **caption** Ela vai mostrar o título da sua tabela acima do cabeçário da tabela. Coloque ela logo depois da tag de abertura de **table**.

Exemplo:
```
<table>
    <caption>Minha tabela é sobre pessoas inteligentes</caption>
    <thead>
        <tr>
            <th>Nome</th>
            <th>Sobrenome</th>
            <th>Email</th>
        </tr>
    </thead>
</table>
```
***

# Estilizando tabelas através do CSS

Essa aula é basicamente sobre CSS básico. Veremos mais sobre isso a frente.

Duas propriedades importantes nós podemos usar aqui.

* **colspan**: Você coloca na tag **th** ou **td**. Permite que você mescle colunas.

* **rowspan**: Você coloca na tag **th** ou **td**. Permite que você mescle linhas.


Vamos o seguinte código como base:
```
<!DOCTYPE html>
<html lang="pt-br">
    <head>
        <meta charset="UTF-8">
        <meta http-equiv="X-UA-Compatible" content="IE=edge">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <title>Trabalhando com Tabelas</title>
        <style>
            table {
                -webkit-box-shadow: 12px 14px 6px 5px rgba(0,0,0,0.24);
                box-shadow: 12px 14px 6px 5px rgba(0,0,0,0.24) ;

            }
            table thead th{
                background-color: black;
                color: white;
            }
            table tfoot td {
                background-color: lightgray;
            }
            table tbody tr:nth-child(even) td {
                background-color: #F1F1F1;
            }
            table tbody tr:hover td {
                background-color: #E9E9E9;
                cursor: pointer;
            }
        </style>
    </head>
    <body>
        <table  width="250" align="center" cellspacing="0" cellpadding="5"> 
            <tfoot>
                <tr>
                    <td>Total</td>
                    <td>6</td>
                </tr>
            </tfoot>
            <tbody>
                <tr>
                    <td>Diogo</td>
                    <td>37</td>
                </tr>
                <tr>
                    <td>Maria</td>
                    <td>34</td>
                </tr>
                <tr>
                    <td>João</td>
                    <td>32</td>
                </tr>
                <tr>
                    <td>Walter</td>
                    <td>24</td>
                </tr>
                <tr>
                    <td>Manoela</td>
                    <td>28</td>
                </tr>
                <tr>
                    <td>Michele</td>
                    <td>26</td>
                </tr>       
            </tbody>
            <thead>
                <tr>
                    <th colspan="2">Minha tabela</th>
                </tr>
                <tr>
                    <th>Nome</th>
                    <th>Idade</th>
                </tr>
            </thead>
        </table>        
    </body>
</html>
```