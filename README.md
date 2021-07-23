# Criando apps mobile com facilidade

Se você mexe com programação web (HTML, CSS e JavaScript) então pode criar aplicativos e jogos mobile do tipo híbridos. Existe uma enorme quantidade de frameworks para a criação de aplicativos mobile. Alguns que trabalham com o código nativo e outros que trabalham com código web e convertem para código nativo, os chamados híbridos.

Como mexo bem pouco com Java e o android-studio é muito pesado para a minha máquina fiz uma boa pesquisa por alternativas.

O Phonegap fazia isso muito bem. Eu instalava sua cli em meu desktop. Com ela criava um projeto simples, então adaptava para um aplicativo web existente (agenda por exemplo) ou para um jogo. Depois que estava funcionando nonavegador eu sompactava e mandava para a nuvem e ele gerava o apk para mim. Eu não precisava ter nem mesmo o Java instalado. Todo este trabalho pesado e trabalhoso de instalar e configurar ele fazia na nuvem.

O Phonegap foi descontinuado pela Adobe. Visitando seu site https://build.phonegap.com/ vi um link para o blog onde explicam por que o descontinuaram. Inclusive indicam alternativas ao Phonegap. A primeira da lista é o Monaco, que é a minha preferida. Com ele criamos aplicativos e jogos mobile de forma similar a que criavamos no Phonegap.

## Resumindo o processo de criação:

- Efetuamos o registro no site - https://monaca.io/
- Podemos criar o aplicativo pela IDE do site ou via cli instalada localmente
- Depois de criar um aplicativo básico então adaptamos para o app ou jogo que queremos e se com a cli enviamos para a nuvem
- Efetuamos as configurações na IDE
- Efetuamos o build para Android, iOS ou Windows
- Ao final podemos baixar o binário ou enviar um link do mesmo para nosso e-mail. É prudente baixar, pois eles não mantém os binários, somente o código

Caso queira tutoriais detalhados sobre como criar um aplicativo e um jogo, inclusive os apks, veja abaixo:

https://github.com/ribafs/mobile/tree/main/Monaca

## URL deste projeto

https://github.com/ribafs/mobile

## Instalação

Regristre-se no site
Crie um projeto do tipo Blank (existem outros)

Acesse o prompt/terminal do seu desktop e execute

npm i -g monaca
monaca login
monaca import

Selecione o projeto criado usando as setas e tecle enter
Entre o nome da pasta onde deseja criar um novo proneto no seu desktop (aqui usei dia-semana) e aguarde...

Se tudo correr bem receberá:

Project is successfully imported from Monaca Cloud!

Então acesse a pasta que indicou

cd dia-semana

E execute (para visualizar no navegador)

monaca preview

Aparecerá apenas 

This is a template for Monaca app.

Agora é o  momento de adaptar um projeto que você tenha para o projeto criado pelo monaca em seu desktop

Eu irei adaptar este pequeno projeto

https://github.com/ribafs/dia-nascimento

Este baixei na pasta

dia-nascimento-gh

Converter para um app mobile tipo Android (O Monaca suporta também iOS e Windows Phone)

O aplicativo rodará em meu desktop e quando concluído farei o upload para o site do Monaca e lá o converterei num APK para usar em meu celular.

Caso esteja usando um linux com o gerenciador de arquivos nemo:

- Abra o nemo
- Tecle F3 para que sejam aebrtos dois paineis um ao lado do outro.
- No painel da esquerda abri dia-nascimento-gh (do github)
- No da direita abri dia-nascimento (do monaca no desktop)

Deve ficar algo assim

![](img/monaca1.png)

Claro que se seu gerenciador não suportar dois paineis deve abrir duas janelas

- No painel da direita abra a pasta www/css
- No da esquerda abra a pasta css
- Copie app.css da esquerda para a direita
- No da esquerda tecle em Backspace para voltar para a apsta dia-nascimento-gh
- No da direita também voltando para a pasta dia-nascimento
- Copie as pastas img e css para o da direita
- No da direita selecione e copie o arquivo service-worker.js para o da direita

Agora é o momento que requer alguma atenção

- Abra o index.html da esquerda em seu editor/IDE de código preferido (precisa suportar UTF-8)
- Abra também o index.html da direita

Selecione e copie para a memória (Ctrl+C) estas linhas do index.html da direita:

    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1, maximum-scale=1, user-scalable=no">
    <meta http-equiv="Content-Security-Policy" content="default-src * data: gap: content: https://ssl.gstatic.com; style-src * 'unsafe-inline'; script-src * 'unsafe-inline' 'unsafe-eval'">
    <script src="components/loader.js"></script>
    <link rel="stylesheet" href="components/loader.css">
    <link rel="stylesheet" href="css/style.css">

Então abra o da esquerda e cole sobre a linha com:

    <meta charset="utf-8">





  > monaca debug        => Run app in the device using Monaca Debugger
  > monaca remote build => Start remote build for iOS/Android/Windows
  > monaca upload       => Upload this project to Monaca Cloud IDE

