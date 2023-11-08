Integrantes:

RM 99389 - Victor Flávio Demarchi Viana
RM 551117 - Lorenzo Gomes Andreata
RM 550695 - Gabriel Ferla
RM 97888 - Vinícius Almeida Bernardino de Souza
RM 98827 - André Coelho Solér


Sprint 4:

	Descrição:
	  Através de sensores de humidade, temperatura e luminosidade, você pode monitorar dados essenciais para bons cuidados de uma planta, e através do Node Red somado a plataforma MQTT TagoIO, monitorar o estado desses sensores e tempo real de qualquer lugar.


	Componentes:

	  - 1 x Protoboard (800 pinos)
	  - 1 x Protoboard (400 pinos)
	  - 1 x Arduino Uno R3
	  - 1 x Fotorresistor
	  - 1 x Sensor de temperatura ou Thermistor
	  - 1 x Sensor de humidade do solo
	  - 1 x Resistor de 10kΩ
	  - 2 x Resistor de 1kΩ
	  - 4 x Resistor de 220Ω
	  - 1 x Diodo
	  - 3 x Potenciômetro de 10kΩ
	  - 3 x LED (cores são opcionais)
	  - 42 x Jumpers Macho/Macho


	Requisitos:

	  - É necessário instalar o Arduino IDE.
	  - É necessário instalar o node-red.
	  - É necessário instalar o node-red-node-serialport.
	  - Possuir um Arduino Uno com o circuito construido (Veja o exemplo em "Scematic Example.png" ou "Schematics.pdf").


	Instruções:

	  - Após montar o circuitos mostrados em "Scematic Example.png" ou "Schematics.pdf" e instalar os programas mencionados acima, é necessário conectar o Arduino Uno á um computador utilizando um cabo USB.
	  - Em seguida, Abrir o Arduino IDE e substituir o código presente pelo conteúdo do arquivo "Arduino Code.txt", depois acessar a aba no canto superior esquerdo chamada "Tools" e definir "Board" como "Arduino Uno" e "Port" como a porta utilizada pelo seu Arduino Uno físico, e por fim, clicar na aba "Sketch" e "Upload".
	  - Após isso, abra o Prompt de Comando do windows e digite "node-red", em seguida acesse "localhost:1880" em qualquer navegador (não feche o prompt).
	  - Arraste o arquivo "Node-Red Flow.json" para dentro do Node-Red (considerando que o módulo de portas serial já foi instalado).
	  - Troque a porta serial clicando duas vezes no nódulo, em seguida no lápis, digite o nome da porta serial do Arduino (com o Arduino IDE fechado), clique na lupinha e selecione a porta digitada.
	  - Caso o nódulo "function" não possua código dentro, copie e cole o conteúdo do arquivo "Node-Red Function.txt" e cole na aba "On Message".
	  - Depois, é necessário se cadastrar no site da TagoIO, ir na aba "Devices", clicar em "Add Device", clicar em "Custom MQTT", trocar o "Device name" por qualquer um que desejar, e clicar em "Create my Device".
	  - Após isso, voltar a aba "Devices" e clicar no recém criado dispositivo, depois trocar o nome da token para o que desejar e clicar em "Generate", por fim clicar nas duas folhas de papel sobrepostas ou clicar sobre o token e copiar seu código.
	  - De volta ao Node Red, clique no nódulo de "mqtt out", em seguida coloque no campo "Topic" o seguinte valor "tago/data/post", após isso clique no lápis e substitua o campo "Server" por "mqtt.tago.io", o campo "ClientID" por qualquer nome que desejar, e no campo "Security", o "Username" deve ser o mesmo que colocou no "ClientID" e a "Password" deve ser o código da token que foi copiada no TagoIO, e finalizar cliando em "Add" e em seguida "Done".
	  - Em seguida clique em "Deploy" no canto superior direito.
	  - Voltando ao TagoIO, clique na aba "Buckets", em seguida no dispositivo que criou, depois em "Variables" e cheque se aparecem "humidPercentage", "tempSens", "luxValue", "humidLed", "tempLed" e "lightLed", como mostrado na imagem "Tago-IO Bucket.png".
	  - Caso não, reveja as etapas anteriores e tente novamente, caso sim, clique no "+" ao lado de "DASHBOARDS", dê um nome para sua tabela e clique em "Create my Dashboard".
	  - Em seguida, entre no modo editor ao clicar no lápis no canto superior direito (caso não o veja é porque já está nele), em seguida clique no "+" no canto superior direito e escolha dentre as opções de "Widgets".
	  - Após feita a escolha, Acesse a aba "Data from" e, no campo "Device", digite o nome do dispositivo que criou, em seguida selecione o campo "Variable" e digite "humidPercentage", depois, clicar em "Create".
	 - Repita o passo anterior mais cinco vezes, porém trocando o valor do campo "Variável" para "tempSens", "luxValue", "humidLed", "tempLed" e "lightLed".
	- Em seguida, clique no dashboard que criou.
	- Tudo feito!