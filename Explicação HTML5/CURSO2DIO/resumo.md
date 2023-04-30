# Formulários HTML
## Aula 1: Panorama Geral

Aulas serão a respeito das seguintes tags:

*   TAG form;
*   TAG input;
*   TAG checkbox & radio;
*   TAG button;
*   TAG select;
*   TAG textarea;

***

## Aula 2: TAG form

Um formulário no seu código HTML é um espaço onde o usuário preenche com os dados dele. Normalmente, esses dados são: nome; sobrenome; email; senha...

É importante que você entenda que formulários andam juntos com os servidores, pois uma vez que os dados são enviados por eles, você precisa de uma lógica para salvá-los no banco de dados do sistema.

Para gerar um formulário voce deve seguir os seguintes passos:

1.   Abra uma tag form: (CÓDIGO ABAIXO)
```
<form>
```

2.  Insira os campos que vai usar no meio dela:  (CÓDIGO ABAIXO)
```
<form>
    Nome: <input type="text" name="name"/><br>
    Idade: <input type="number" name="age"/><br>
    Senha: <input type="password" name="password"/><br>
    <button type="submit">Enviar</button>
```

3.  Feche uma tag form:  (CÓDIGO ABAIXO)
```
</form>
```
O código de exemplo final deve estar assim: 
```
<form>
    Nome: <input type="text" name="name"/><br>
    Idade: <input type="number" name="age"/><br>
    Senha: <input type="password" name="password"/><br>
    <button type="submit">Enviar</button>
</form>
```
Vamos focar apenas na tag **form**. As outras tags serão melhor abordadas mais a frente.

A tag **form** possui um atributo chamado **name**. Esse atributo é global. Isso quer dizer que podemos usá-lo em qualquer tag HTML. Geralmente o usamos para identificar o elemento que será tratado no backend. Dito isso, vamos colocar o valor chamado signup no atributo name: (CÓDIGO ABAIXO)

```
<form name="signup">
    Nome: <input type="text" name="name"/><br>
    Idade: <input type="number" name="age"/><br>
    Senha: <input type="password" name="password"/><br>
    <button type="submit">Enviar</button>
</form>
```

Nós também temos outro atributo chamado **action** aqui. Ele determina para onde os dados são enviados. Como assim? O site para o qual os dados serão enviados: (CÓDIGO ABAIXO) 
```
<form name="signup" action="https://meusite.com.br/signup">
    Nome: <input type="text" name="name"/><br>
    Idade: <input type="number" name="age"/><br>
    Senha: <input type="password" name="password"/><br>
    <button type="submit">Enviar</button>
</form>
```
Outro atributo que podemos utilizar aqui é o **method**. Diferente de **action** e **name**, onde você pode escrever o que quiser, só existem dois valores possíveis para este atributo, **GET** ou **POST**. A principal diferença entre eles será que quando você enviar os dados para algum lugar seu comportamento será diferente. Se você usar o **GET**, ele envia os dados para o site definido no action, porém, mostra tudo o que foi digitado dentro do formulário na url. Se você estiver usando o **POST**, ele não faz isso. Ele incapsula informação e envia. Em resumo, se você estiver trabalhando com dados sensíveis dentro do formulário como senhas, NÃO USE o GET. (CÓDIGO ABAIXO)

Vamos mudar o valor de **action** para **#**, simplesmente, para evitar erros já que o site é meramente ilustrativo.

```
<form name="signup" action="#" method="POST">
    Nome: <input type="text" name="name"/><br>
    Idade: <input type="number" name="age"/><br>
    Senha: <input type="password" name="password"/><br>
    <button type="submit">Enviar</button>
</form>
```
Podemos usar o atributo **target** aqui. Ele funciona igual na tag **a**. Ou seja, se escolher o valor **_blank** para o atributo os dados serão enviados por outra aba que será aberta. (CÓDIGO ABAIXO)

```
<form name="signup" action="#" method="POST" target="_blank">
    Nome: <input type="text" name="name"/><br>
    Idade: <input type="number" name="age"/><br>
    Senha: <input type="password" name="password"/><br>
    <button type="submit">Enviar</button>
</form>
```

Outro atributo que podemos usar aqui também é o **autocomplete**. Assim como **method**, podemos adicionar apenas dois valores aqui, **off** ou **on**. Como o próprio nome diz ele autocompleta as informações, mas que informações? Já percebeu que quando você acessa um site pela primeira vez, faz um cadastro, digita uma senha, o seu navegador te pergunta se você quer salvar aquela informação, daí quando você acessa de novo o mesmo site o navegador autocompleta para você? Então, se eu deixar o autocomplete desligado(**off**), isto não será possível. Por padrão esse atributo mantém **on**.    

```
<form name="signup" action="#" autocomplete="off" method="POST" target="_blank">
    Nome: <input type="text" name="name"/><br>
    Idade: <input type="number" name="age"/><br>
    Senha: <input type="password" name="password"/><br>
    <button type="submit">Enviar</button>
</form>
```
Podemos adicionar eventos JavaScript com o atributo **onsubmit**:

```
<form name="signup" action="#" onsubmit="alert('Enviado com sucesso!');" autocomplete="off" method="POST" target="_blank">
    Nome: <input type="text" name="name"/><br>
    Idade: <input type="number" name="age"/><br>
    Senha: <input type="password" name="password"/><br>
    <button type="submit">Enviar</button>
</form>
```
***

## Aula 3: TAG input

Antes da gente começar, vamos relembrar o código da aula anterior. Você se lembra que deixamos um pouco de texto dentro da tag **form** que estava sem uma tag específica para ele?

Código da aula anterior:
```
<form name="signup" action="#" onsubmit="alert('Enviado com sucesso!');" autocomplete="off" method="POST" target="_blank">
    Nome: <input type="text" name="name"/><br>
    Idade: <input type="number" name="age"/><br>
    Senha: <input type="password" name="password"/><br>
    <button type="submit">Enviar</button>
</form>
```
Note as palavras: Nome, Idade e Senha. Isso não está correto. Nestes casos, onde inserimos texto ao lado de uma barra input, utilizamos a tag **label** para incluir o conteúdo dentro. Vamos fazer isso agora!

```
<form name="signup" action="#" onsubmit="alert('Enviado com sucesso!');" autocomplete="off" method="POST" target="_blank">
    <label>Nome:</label><input type="text" name="name"/><br>
    <label>Idade:</label><input type="number" name="age"/><br>
    <label>Senha:</label><input type="password" name="password"/><br>
    <button type="submit">Enviar</button>
</form>
```

Agora, vamos ver cada um dos tipos de input que definimos através do atributo **type**:

*   **text**: Este valor permite que o usuário insira texto livremente dentro da tag;

```
<input type="text"/>
```

*   **number**: Este valor aceita somente caracteres numéricos; Quando definimos o valor do atributo **type** como **number**, podemos definir outros dois atributos, **min** e **max**. Elas definem o número mínimo e máximo da tag input. Outro atributo que podemos usar com **number** é o **step**. Ele faz com que ao clicarmos no ícone para cima ou para baixo, os números vão em intervalos definidos em **step**.

```
<input type="number" min="0" max="120" step="5"/>
```

*   **button**: Este atributo não é muito utilizado, pois faz a mesma cosia que uma tag **button** ;

As duas linhas abaixo fazem a mesma coisa:

```
<input type="button" value"Enviar"/>
<button type="submit">Enviar</button>
```

*   **range**: Cria um campo scroll. Você pode definir as propriedades **min**, **max** e **value** aqui. Como no **number**, **min** e **max** definirão o mínimo e máximo da barra scroll. **value** definirá onde a barra iniciará.

```
<input type="range" min="10" max="50" value="30"/>
```

*   **color**: Cria uma paleta de cores;

```
<input type="color"/>
```

*   **email**: Cria uma barra de input exclusiva para email. Ela faz algumas validações, por exemplo, você não será capaz de enviar nada que não tenha @ por exemplo. Não é muito utilizada, pois nós costumamos usar os nossos próprios métodos de validação.

```
<input type="email"/>
```

*   **url**:  Cria uma barra de input exclusiva para url's. Não permite que você envie uma url sem o https://, por exemplo.

```
<input type="url"/>
```

*   **date**: Ele cria uma barra inserção de data no formato correto. Ele usa o idioma padrão do seu navegador para definir o formato de inserção data mais adequado.

```
<input type="date"/>
```

*   **week**: Crie uma barra para escolher a semana do ano desejado com as validações corretas. SÓ FUNCIONA NO GOOGLE CHROME E NO MICROSOFT EDGE.

```
<input type="week"/>
```

*   **month**: Crie uma barra para escolher o mês do ano desejado com as validações corretas. SÓ FUNCIONA NO GOOGLE CHROME E NO MICROSOFT EDGE.

```
<input type="month"/>
```

*   **checkbox**: Crie uma caixa quadrada de seleção.

```
<input type="checkbox"/>
```

*   **radio**: Crie um círculo de seleção. Funciona parecido com o checkbox, mas permite que só um elemento seja selecionado. Mas isso se eu tiver inputs com o valor **radio** em locais diferentes? Para usar o radio você tem usar o atributo **name** com valores iguais para as checkbox relacionadas.

```
<input type="radio" name="aceita"/>
<input type="radio" name="aceita"/>    
```

*   **password**: Este valor faz com que seu contéudo fica em formato de bolinhas omitindo o conteúdo digitado da visão do usuário.

```
<input type="password"/>
```

*   **hidden**: É um campo de input que fica invisível para o usuário. Não pode ser visto. Pode ser necessário enviar uma informação única que o usuário não veja as vezes.

```
<input type="hidden"/>
```

*   **file**: É um campo para envio de arquivos. Fazer uploads do seu pc para o site. Você pode adicionar o atributo **multiple** também. Ele permitirá que você envio múltiplos arquivos. Do contrário, só uma será permitido.

```
<input type="file" multiple/>
```

*   **search**: Crie um campo de busca com um x para apagar. Ideal para campos de pesquisa. SÓ FUNCIONA NO GOOGLE CHROME E NO MICROSOFT EDGE.

```
<input type="search"/>
```

***

## Aula4: CHECKBOX E RADIO

Vamos usar o seguinte código para exemplificar tudo aqui.

```
<!DOCTYPE html>
<html lang="pt-br">
    <head>
        <meta charset="UTF-8">
        <meta http-equiv="X-UA-Compatible" content="IE=edge">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <title>Formulário de Cadastro 2</title>
    </head>
    <body>
        <form method="GET">
            <h3>Você selecionou: Pizza de Calabresa</h3>
            <p>Quais opcionais você deseja?</p>
            <input type="checkbox" name="" value="queijo"/> + queijo <br>
            <input type="checkbox" name="" value="calabresa"/> + calabresa <br>
            <input type="checkbox" name="" value="cebola"/> + cebola <br>
            <input type="checkbox" name="" value="azeitona"/> + azeitona <br>
            <p>Borda recheada?</p>
            <input type="radio" name="" value="sim" />Sim<br>
            <input type="radio" name="" value="não" />Não<br>
            <p>Bebida</p>
            <input type="radio" name="" value="suco"/>Suco<br>
            <input type="radio" name="" value="refrigerante"/>Refrigerante<br>
            <input type="radio" name="" value="agua"/>Água<br>
            <input type="radio" name="" value="nenhum"/>Nenhum<br>
            <button type="submit">Enviar pedido</button>
        </form>
    </body>
</html>
```

Por padrão, as checkbox são usadas para seleção de muitos itens sendo que eu seleciono todos que eu quiser. No caso de radio não é assim. A idéia do radio é que quando eu escolho um item, só ele fica selecionado, mas no momento, o código não está funcionando assim. Por quê?

Eu preciso definir a propriedade name, de forma que ela fica igual para todas as checkbox relacionadas dentro da página. Vamos fazer isso agora!

Abaixo, só estão as partes com radio no input.

```
<input type="radio" name="bordapizza" value="sim" />Sim<br>
<input type="radio" name="bordapizza" value="não" />Não<br>

<!--  -->

<input type="radio" name="bebida" value="suco"/>Suco<br>
<input type="radio" name="bebida" value="refrigerante"/>Refrigerante<br>
<input type="radio" name="bebida" value="agua"/>Água<br>
<input type="radio" name="bebida" value="nenhum"/>Nenhum<br>
<button type="submit">Enviar pedido</button>
```

No caso da checkbox, a ideia é que você possa selecionar quantos valores quiser, ainda assim, quando passamos seus valores para o servidor, não queremos passar 1 a 1, queremos passar todos de uma vez só. Por isso, vamos colocar um name nelas também. 

```
<input type="checkbox" name="opcionais" value="queijo"/> + queijo <br>
<input type="checkbox" name="opcionais" value="calabresa"/> + calabresa <br>
<input type="checkbox" name="opcionais" value="cebola"/> + cebola <br>
<input type="checkbox" name="opcionais" value="azeitona"/> + azeitona <br>
```

Porém, se mandarmos este código desta forma, as linguagens backend vão entender que opcional é uma variável que trocou de valor 4 vezes: Seu primeiro valor era queijo e o último, azeitona, mas é realmente isso o que queremos fazer? Claro que não!

Nós queremos mandar uma lista com os valores relacionados. Para isso vamos adicionar colchetes na frente de opcionais, como abaixo:
```
<input type="checkbox" name="opcionais[]" value="queijo"/> + queijo <br>
<input type="checkbox" name="opcionais[]" value="calabresa"/> + calabresa <br>
<input type="checkbox" name="opcionais[]" value="cebola"/> + cebola <br>
<input type="checkbox" name="opcionais[]" value="azeitona"/> + azeitona <br>
```

Ainda assim, é recomendado que quando você trabalha com checkbox, use o método **POST** na tag **form**, ao invés de **GET**, vamos mudar isso:

```
<form method="POST">
```

Falando ainda sobre checkbox, nós podemos usar um atributo nelas chamado **disabled**. Faz com que a checkbox não seja clicável.

Exemplo:
```
<input type="checkbox" disabled/>
```

***

## Aula5: Button e Seus Tipos

Vamos o seguinte código como base:
```
<!DOCTYPE html>
<html lang="pt-br">
    <head>
        <meta charset="UTF-8">
        <meta http-equiv="X-UA-Compatible" content="IE=edge">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <title>Formulário de Cadastro 3</title>
    </head>
    <body>
        <form method="get">
            <label>Nome:</label><input type="text" name="name"/>
            <label>Idade:</label><input type="number" name="age"/>
            <label>Senha:</label><input type="password" name="password"/>        
        </form>      
    </body>
</html>
```

Nesta aula, vamos falar sobre os tipos de botões definidos pela tag **button**. Nós definimos cada tipo usando o atributo **type**. Nós podemos ter 3 tipos de botões diferentes: **button**, **reset** e **submit**. Estes são os 3 valores que podemos colocar dentro do atributo **type**. Vamos conferir cada um deles agora.

*   **button**: Vamos começar com o tipo **button**. Este valor é um tipo de botão que não faz nada, a menos que você aplique um código JavaScript nele. Faça o este:

```
<button type="button">Clicável</button>
```
Veja que é um botão inútil. Não faz nada. Agora, se usarmos os atributos que permitem aplicar JavaScript diretamente sobre elemento, é outra história. Vamos fazer um teste usando o atributo **onclick**:

```
<button type="button" onclick="alert('Cliquei aqui!')">Clicável</button>
```

*   **reset**: Como o próprio nome diz, ele limpa todos os campos preenchidos da tag **form** que ele está dentro.

Faça o teste. Preencha todos os valores e depois clique no botão.

```
<form method="get">
    <label>Nome:</label><input type="text" name="name"/>
    <label>Idade:</label><input type="number" name="age"/>
    <label>Senha:</label><input type="password" name="password"/>
    <button type="reset">Limpar?</button>        
</form>   
```
*   **submit**: Como o próprio nome diz, ele envia os dados do formulário que ele está dentro.

Faça o teste. Preencha todos os valores e depois clique no botão.

```
<form method="get">
    <label>Nome:</label><input type="text" name="name"/>
    <label>Idade:</label><input type="number" name="age"/>
    <label>Senha:</label><input type="password" name="password"/>
    <button type="type">Enviar</button>        
</form>   
```
***

## Aula6: Select e Seus Tipos

Vamos o seguinte código como base aqui:

```
<!DOCTYPE html>
<html lang="pt-br">
    <head>
        <meta charset="UTF-8">
        <meta http-equiv="X-UA-Compatible" content="IE=edge">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <title>Formulário de Cadastro 4</title>
    </head>
    <body>
        <form method="get">
            <label>Nome:</label><input type="text" name="name"/><br>
            <label>Cargo:</label><input type="text" name="role"/><br>
            <label>Assunto:</label><input type="text" name="subject"/><br>      
            <button type="submit">Enviar</button>        
        </form>      
    </body>
</html>
```

Há casos onde a gente tem um conjunto de opções pré-definidas para que o usuário escolha. Por exemplo, nós temos um campo acima chamado Cargo. Geralmente, quando nós pedimos para um usuário inserir um cargo, ele não pode inserir qualquer coisa. Existe um número limitado de opções. Neste caso, usaremos um tag chamada **select** que nos permite limitar o usuário há um número limitado de opções.

Resumindo, não é uma boa prática deixar o campo **Cargo** livre para o usuário selecionar o que quiser. Vamos resolver isso! Vamos alterar o campo cargo, que é um input normal, para um checkbox:


Código anterior:
```
<label>Cargo:</label><input type="text" name="role"/><br>
```

Código posterior:
```
<select name="role">
    <option value="">Selecione o cargo</option>
    <option value="gerente">Gerente</option>
    <option value="diretor">Diretor</option>
    <option value="presidente">Presidente</option>
</select><br>
```
Note que precisamos passar um **name** para **select**. 

Veja também que a tag **select** exige o uso das tag filha chamada **option**. Cada uma das opções deve estar dentro de uma tag **option** e cada uma das opções deve ter um valor definido(**value**). Veja que a primeira opção é um valor nulo. Nós vamos usá-lo como padrão para o usuário ver esse valor assim que abrir o formulário.

Código anterior:
```
<option value="">Selecione o cargo</option>
```

Código posterior:
```
<option value="" selected>Selecione o cargo</option>
```

Adicionando o atributo **selected**, assim que o formulário for aberto, a opção selecionada será a tag que carrega esse atributo. Se não definirmos isso a tag **selected** carregará vazia.

Agora, perceba que o valor *Selecione o cargo* deveria ser um valor nulo. Primeiramente, nós queríamos que esse valor fosse exibido assim que o usuário se deparasse com o formulário e isso já foi feito, mas precisamos torná-lo nulo, caso contrário, o usuário poderá selecioná-lo para o servidor. Vamos corrigir isso!

Código anterior:
```
<option value="" selected>Selecione o cargo</option>
```

Código posterior:
```
<option value="" selected disabled>Selecione o cargo</option>
```
Agora está correto. O usuário verá esse valor selecionado assim que abrir o formulário, mas não poderá selecioná-lo.

Se quisermos que o usuário seja capaz de selecionar mais de uma opção, basta adicionar o atributo **multiple** à tag **select**

Código anterior:
```
<select name="role">
```

Código posterior:
```
<select name="role" multiple>
```
## Aula7: Textarea

Nós vamos usar o seguinte código base aqui.

```
<!DOCTYPE html>
<html lang="pt-br">
    <head>
        <meta charset="UTF-8">
        <meta http-equiv="X-UA-Compatible" content="IE=edge">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <title>Formulário de Cadastro 4</title>
    </head>
    <body>
        <form method="get">
            <label>Nome:</label><input type="text" name="name"/><br>
            <label>Cargo:</label>
            <select name="cargo">
                <option selected value="">Selecione o cargo</option>
                <option value="gerente">Gerente</option>
                <option value="diretor">Diretor</option>
                <option value="presidente">Presidente</option>
            </select><br>
            <label>Assunto:</label><input type="text" name="subject"/><br>      
            <button type="submit">Enviar</button>        
        </form>      
    </body>
</html>
```

Vamos estudar a tag **textarea** agora. Essa tag é usada para colocar informações aleatórias lá dentro. Geralmente, uma mensagem, uma avaliação, a explicação de um problema, etc...

Vamos adicionar um texto chamado *Mensagem* como título da nossa **textarea** abaixo de botão.
```
<label>Mensagem:</label>
```
Vamos também adicionar a ** ** dela.

```
<textarea name="mensagem"></textarea>
```

Veja que as textareas são redimensionáveis. A única forma de alterar isso é através do CSS. Você pode definir a quantidade de linhas que ela iniciará com o atributo **rows**.

```
<textarea rows="10" name="mensagem"></textarea>
```

Você pode fazer o mesmo com as colunas:

```
<textarea rows="10" cols="10" name="mensagem"></textarea>
```