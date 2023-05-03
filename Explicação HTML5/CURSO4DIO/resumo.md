# Tags de mídia

Vamos ver tudo relacionado à tags de mídia, ou seja, aúdio, vídeo, imagens, etc...

***

## Tag img

A tag **img** serve para adicionar imagens. Ela tem o atributo **src** que serve para adicionar fotos ao seu site, sejam externas, urls, ou internas, o caminho da imagem.

Outro atributo improtante é **alt**. É muito bom para acessibilidade e SEO do seu site. Se a imagem for carregada, ou não puder ser lida por algum motivo, um robô pode descreve-la.

Outro atributo improtante é **title**. Quando você passar o mouse sobre a imagem, ele vai mostrar um balão descrevendo a imagem. 
Você pode dimensionar largura e altura através dos atributos **width** e **height** respectivamente. Você coloca um valor numérico. 
OBS: SE VOCÊ SÓ AJUSTAR A LARGURA, A ALTURA VAI DIMINUIR PARA MANTER A PROPORÇÃO.

Exemplo:
```
<img src="imagem.png" alt="Essa é a minha imagem" title="Clique aqui para ver mais informações"/>
```
Precisamos entender também os formatos da imagens. Gif é muito pesado para conseguir uma resolução satisfatória, jgp comprime a imagem o que a faz perder qualidade e  png é o melhor. svg é limitado a imagens mais opacas, mas tende a ser melhor. Se usar o svg, certifique-se de usar a tag **svg**

***
## Tag audio

Tag exclusiva para aúdio.

Ela é uma tag que você precisa abrir e fechar. Você precisa usar a tag filha chamada **source** com o atributo **src** para mostrar o caminho da imagem.

Se você quiser mostrar um texto para caso a imagem não carregue, basta escreve-lo abaixo de **source**

Você também pode ajustar **controls** para exibir os controles básicos de aúdio para o usuário como aumentar volume, barra de execução, etc. Caso nâo o coloque, não vai ter barra para mostrar o aúdio. Se você colocar **autoplay**, o aúdio iniciará sozinho. 

Exemplo:
```
<audio controls autoplay >
    <source src="musica.mp3" />
    Seu navegador não tem suporte a esse aúdio.
</audio>
```
***

## Tag video

Agora, vamos falar sobre a tag vídeo usada para adicionar vídeo no seu website. Assim como na audio, cada navegador renderiza o player de uma forma.

Funciona igual à tag **audio**. 
*  É uma tag que abre e fecha;
*  O link do vídeo, ou caminho do vídeo no seu computador, precisar ser informado dentro da tag **source** que é filha de **video**;
*  Na tag **source**, você tem o atributo **source** onde você passa o caminho do vídeo; 
*  Caso o vídeo não possa ser renderizado, você pode deixar uma mensagem para ser mostrada abaixo da tag source;

Exemplo:
```
<video controls autoplay >
    <source src="video.mp3" />
    Seu navegador não tem suporte a esse vídeo.
</video>
```

Por padrão, o **controls** de **video** já é true. Isso significa que os controles de vídeo serão mostrado ao usuário.

As vezes, alguns navegadores não suporta o formato de vídeo **mp4**. Nestes casos, o ideal é usar o segundo formato de vídeo, o formato **webm**. Daí, caso o navegador não consiga carregar o **mp4**, ele executará o segundo vídeo.

Exemplo:
```
<video controls autoplay >
    <source src="video.mp3" />
    <source src="video2.webm" />
    Seu navegador não tem suporte a esse vídeo.
</video>
```

***

## Tag track

Essa é uma tag que veio para auxiliar a tag **video**. Ela é usada para colocar legendas nos vídeos. Você também pode gerar os *chapters* ou *capítulos* através dessa tag. *Chapters* nada mais são do que uma forma de definir o tempo do vídeo que a legenda aparecerá. 

Geralmente, os *chapters* são gerados em arquivos no formato **.vtt**.

Falando sobre essa tag, assim como **source**, ela é uma tag só de abertura. Dentro dela, você precisa definir alguns atributos:

*   **src**: O arquivo fonte que carregará a legenda.

* **kind**: Define o tipo de legenda. Não existe apenas um tipo de legenda para vídeo. Nós podemos ter legendas que descrevem o as pessoas estão falando; legendas que descrevem o local do evento; legendas que narram o que será abordado no vídeo e assim por diante. Temos alguns valores válidos aqui:

   *   **captions**: Descreve as falas das pessoas.
   
   *   **chapters**: Ele narra os fatos dos vídeos. Mostra o que será abordado no vídeo.
   
   *   **descriptions**: Define o que leitor de tela vai ler.
   
   *   **metadata**: Dados adicionais para SEO.
   
   *   **subtitles**: Descreve mais sobre vídeo. Descreve o local em que os eventos ocorrem no vídeo.

*   **srclang**: Define a língua da legenda.

*   **default**: Define a legenda padrão que aparecerá quando o usuário ativá-la.

Por fim, eu posso ter mais de uma legenda.

Exemplo:
```
<video controls autoplay >
    <source src="video.mp3" />
    <source src="video2.webm" />
    <track src="legenda.vtt" kind="captions" srclang="en"/>
    <track src="legendabrasileira.vtt" kind="captions" srclang="pt-br"/>
    Seu navegador não tem suporte a esse vídeo.
</video>
```

***

## Tag iframe

Como já mencionado, o **iframe** permite que você adicione páginas externas ao seu html. No caso do YouTube, você pode clicar em compartilhar, no vídeo que quer colocar, no código, depois em incorporar. Ele vai gerar um iframe para você.