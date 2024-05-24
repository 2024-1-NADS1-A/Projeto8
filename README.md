# FECAP - Fundação de Comércio Álvares Penteado

<p align="center">
<a href= "https://www.fecap.br/"><img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRhZPrRa89Kma0ZZogxm0pi-tCn_TLKeHGVxywp-LXAFGR3B1DPouAJYHgKZGV0XTEf4AE&usqp=CAU" alt="FECAP - Fundação de Comércio Álvares Penteado" border="0"></a>
</p>

# Nome do Projeto
Bicicleta inteligente
## Nome do Grupo
MNR
## Integrantes: <a href="https://www.linkedin.com/in/nathan-lucena-0a271a26a">Nathan Silva de Lucena</a>, <a href="https://www.linkedin.com/in/raissa-elias-873178232/">Raissa Elias Silva</a>, <a href="https://www.linkedin.com/in/marcella-santana-b76883262/">Marcella Santana Gonçalves Diniz Rocha</a>

## Professores Orientadores: <a href="https://www.linkedin.com/in/victorbarq/">Victor Bruno Alexander Rosetti de Quiroz</a>, <a href="https://www.linkedin.com/in/adriano-valente-534576135/">Adriano Felix Valente</a>

## Descrição

<p align="center">
<img src="https://pix4free.org/assets/library/2021-01-20/originals/game.jpg" alt="NOME DO JOGO" border="0">
  Game by <a href="http://www.nyphotographic.com/">Nick Youngson</a> <a rel="license" href="https://creativecommons.org/licenses/by-sa/3.0/">CC BY-SA 3.0</a> <a href="http://pix4free.org/">Pix4free</a>
</p>


De um a dois parágrafos sobre o que é seu projeto e o que ele faz.
<br><br>
Uma bicicleta 'inteligente' que conta a velocidade em km/h e os batimentos cardíacaos em bpm por meio de sensores aplicados em um arduíno esp32 que envia essas informações em tempo real a um app via plataforma Blynk e perrmite que o usuário monitore seu desempenho a qualquer instante. O projeto tem como objetivo o monitoramento de desempenho mas, também é possível ajudar pessoas que procuram o ciclismo como um exercício para melhorar a saúde e investir no bem-estar, e, assim, progredir a qualidade de vida. 
<br><br>
May the force be with you!
<br><br>

## 🛠 Estrutura de pastas

-Raiz<br>
|<br>
|-->documentos<br>
  &emsp;|-->antigos<br>
  &emsp;|Documentação.docx<br>
|-->executáveis<br>
  &emsp;|-->windows<br>
  &emsp;|-->android<br>
  &emsp;|-->HTML<br>
|-->imagens<br>
|-->src<br>
  &emsp;|-->Backend<br>
  &emsp;|-->Frontend<br>
|readme.md<br>

A pasta raiz contem dois arquivos que devem ser alterados:

<b>README.MD</b>: Arquivo que serve como guia e explicação geral sobre seu projeto. O mesmo que você está lendo agora.

Há também 4 pastas que seguem da seguinte forma:

<b>documentos</b>: Toda a documentação estará nesta pasta.

<b>imagens</b>: Imagens do sistema

<b>src</b>: Pasta que contém o código fonte.

## 🛠 Instalação Arduino IDE
Abra seu navegador e vá para o site do arduino em arduino.cc, navegue até a seção de downloads: No menu superior, clique em Software e depos em Downloadds.
Selecione seu sistema operacional, clique no botão paara baixar o instalador do Arduino IDE para Windows, após o download, abra o arquivo '.exe' baixado. Aceite os termos de uso: Na janelado instalador, você precisará aceitar os termos de uso. Escolha os componentes a serem instalados e o diretório de instalação: Você pode escolhar o local onde deseja instalar o Arduino IDE ou usar o caminho padrão sugerido. Depois clique em instalar e aguarde a conclusão do processo, após a instalação, clique em concluir e o Arduino IDE estará pronto para o uso.
## 🛠 Configuração do esp32 no Arduino IDE
Para configurar o Arduino IDE para ESP32, abra o Arduino IDE que você acabou de instalar, adicionar o url do gerenciador de placas vá em Arquivos > Preferências e no campo "URLs adicionais para Gerenciadores de Placas", adicione a seguinte URL: https://raw.githubusercontent.com/espressif/arduino-esp32/gh-pages/package_esp32_index.json
Abrir o Gerenciador de Placas: Vá em''Ferramentas'>'Placas'>'Gerenciador de Placas'. Instalar o pacote ESP32, na janela do gerenciador de placas, procure por esp32 e instale o pacote esp32 by Espressif Systems. Após a instalação, vá em ferramentas > placa e selecione a placa esp32 que você está utilizando ( por exemplo, ESP32 Dev Module).

Conecte a sua placa esp32 ao computador usando um cabo USB, Selecione a porta serial: Vá em ferramentas > porta e selecione a porta serial correspondente ao seu esp32.
Depois vá em arquivo> exemplos > wifi > wifiscan ( ou qualquer outro exemplo que você prefira). Enviar o código para a placa, clique no botão upload ( seta para a direita) para compilar e enviar o código para a placa esp32.
## 🛠 Definição do código do arduíno esp32 
Para o arduíno esp32 definir seu código e conseguir a rede WiFi conectada a este, é preciso primeiro conseguir suas bibliotecas no próprio site do Arduino IDE. As bibliotecas usadas serão https://downloads.arduino.cc/libraries/github.com/iliaslamprou/Virtuino_library_for_all_ESP8266_and_ESP32_boards-1.7.2.zip para o arduíno esp32, https://downloads.arduino.cc/libraries/github.com/blynkkk/Blynk-1.3.2.zip para a biblioteca blynk, https://downloads.arduino.cc/libraries/github.com/arduino-libraries/WiFi-1.2.7.zip para o wifi. Para instalar as bibliotecas é possível através de sketch > include library > add zip library. Definir, no começo do código, o id do blynk, assim como o name, e o token necessário. Definir também Blynk print serial para desativar prints e economizar espaço. Com as bibliotecas instaladas, agora é necessário inclui-lás, no código. Agora, definir variáveis que leiam as credencias de WiFi por meio do nome da rede e a senha para que o arduíno os leia. Definir os pinos para os sensores como o de velocidade pino 4 e o frequência cardíaca pino 32. Em seguida, inserir variáveis para o cálculo de velocidade, com uma que armazene o último tempo em que o sensor foi ativdo, outra que armazene o intervalo de tempo entre as duas ativações do sensor, outra que armazene o último tempo de debounce (frequência com que uma função é executada em resposta a um evento), uma variável que leia o delay do debounce em milissegundos e uma última que leve em consideração a circunferência da roda para fazer o cálculo da velocidade. 
Necessário criar um objeto do tipo BlynkTimer para gerenciar as temporizações e em seguida uma função de interrupção para o sensor de velocidade. Na função, aplicar variáveis que leiam e obtém o tempo atual em milissegundos, que verifiquem se o tempo do debounce passou, calculem o intervalo de tempo entre duas ativações do sensor, que atualize o último tempo em que o sensor foi ativado e que também atualize o último tempo de debounce. 

## 🛠 Instalação do Blynk
Vá para o site do Blynk.io e clique em sign up para criar uma conta. Se você já tem uma conta, faça o login. Após fazer o login, vá para a seção Dashboard e clique em Create new para criar um novo projeto, selecione o tipo de dispositivo que você está usando (Arduino, ESP32, etc.) e o tipo de conexão (wifi, ethernet, bluetooth, etc). Depois de selecionar o tipo de dispositivo, você receberá um token de autentificação via e-mail. Este token é usado para vincular seu dispositivo ao aplicativo Blynk. Copie o código fornecido no aplicativo Blynk para o Arduino IDE, insira o token de autentificação no código onde indicado e faça o upload para o seu dispositivo, após carregar o código, seu dispositivo deve estar conectado ao aplicativo Blynk e pronto para uso. Teste os widgets para garantir que tudo funcione conforme o esperado.





```sh
Coloque código do prompt de comando se for necessário
```

```
## 🗃 Histórico de lançamentos

A cada atualização os detalhes devem ser lançados aqui.

* 0.2.1 - 25/01/2022
    * MUDANÇA: Atualização de docs (código do módulo permanece inalterado)
* 0.2.0 - 15/01/2022
    * MUDANÇA: Remove `setDefaultXYZ()`
    * ADD: Adiciona `init()`
* 0.1.1 - 11/01/2022
    * CONSERTADO: Crash quando chama `baz()` (Obrigado @NomeDoContribuidorGeneroso!)
* 0.1.0 - 10/01/2022
    * O primeiro lançamento adequado
    * MUDANÇA: Renomeia `foo()` para `bar()`
* 0.0.1 - 01/01/2022
    * Trabalho em andamento

## 📋 Licença/License
<p xmlns:cc="http://creativecommons.org/ns#" xmlns:dct="http://purl.org/dc/terms/"><a property="dct:title" rel="cc:attributionURL" href="https://github.com/2024-1-NADS1-A/Projeto8">Bicicleta inteligente</a> by <a rel="cc:attributionURL dct:creator" property="cc:attributionName" href="https://github.com/2024-1-NADS1-A/Projeto8">FECAP, Nathan Silva de Lucena, Marcella Santana Gonçalves Diniz Rocha, Raissa Elias Silva</a> is licensed under <a href="https://creativecommons.org/licenses/by/4.0/?ref=chooser-v1" target="_blank" rel="license noopener noreferrer" style="display:inline-block;">Creative Commons Attribution 4.0 International<img style="height:22px!important;margin-left:3px;vertical-align:text-bottom;" src="https://mirrors.creativecommons.org/presskit/icons/cc.svg?ref=chooser-v1" alt=""><img style="height:22px!important;margin-left:3px;vertical-align:text-bottom;" src="https://mirrors.creativecommons.org/presskit/icons/by.svg?ref=chooser-v1" alt=""></a></p>

## 🎓 Referências

Aqui estão as referências usadas no projeto.

1. <https://github.com/iuricode/readme-template>
2. <https://github.com/gabrieldejesus/readme-model>
3. <https://creativecommons.org/share-your-work/>
4. <https://freesound.org/>
5. Músicas por: <a href="https://freesound.org/people/DaveJf/sounds/616544/"> DaveJf </a> e <a href="https://freesound.org/people/DRFX/sounds/338986/"> DRFX </a> ambas com Licença CC 0.
