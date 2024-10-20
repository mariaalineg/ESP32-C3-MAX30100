# ESP32-C3 Mini e MAX30100 - Monitor de Batimentos e SpO2

Este projeto utiliza o **ESP32-C3 Mini** e o sensor **MAX30100** para medir os batimentos cardíacos (BPM) e a saturação de oxigênio no sangue (SpO2). Os dados são exibidos em uma página web hospedada pelo ESP32.

## Funcionalidades
- Medição de **BPM** e **SpO2** em tempo real.
- Visualização das medições através de uma página web simples.
- Conexão à rede Wi-Fi para acessar remotamente.

## Requisitos

### Hardware
- ESP32-C3 Mini.
- Sensor MAX30100 (com ajustes de pull-up para SDA e SCL).
- Resistores de pull-up externos de 4.7kΩ para SDA e SCL.

### Software
- Arduino IDE (com suporte à placa ESP32-C3).
- Biblioteca [WiFi](https://www.arduino.cc/en/Reference/WiFi).
- Biblioteca [WebServer](https://github.com/espressif/arduino-esp32/tree/master/libraries/WebServer).
- Biblioteca [MAX30100_PulseOximeter](https://github.com/oxullo/Arduino-MAX30100).

## Instalação e Configuração

### 1. Instale o suporte à placa ESP32-C3 no Arduino IDE
- Abra o Arduino IDE e vá em **File > Preferences**.
- No campo **Additional Board Manager URLs**, adicione o seguinte link:
- https://raw.githubusercontent.com/espressif/arduino-esp32/gh-pages/package_esp32_index.json
- Vá em **Tools > Board > Boards Manager** e procure por **esp32**.
- Instale o pacote de placas **esp32**.

### 2. Instale as bibliotecas necessárias
- Vá em **Sketch > Include Library > Manage Libraries**.
- Procure por **MAX30100_PulseOximeter** e instale.
- Procure por **WebServer** e instale.

### 3. Conecte o hardware
- Conecte o sensor MAX30100 aos pinos I2C do ESP32-C3 (GPIO 8 = SDA, GPIO 9 = SCL).
- Adicione resistores de pull-up de 4.7kΩ entre os pinos SDA/SCL e 3.3V.

### 4. Configure o código
No arquivo `ESP32-C3-MAX30100.ino`, insira as informações da sua rede Wi-Fi:
```cpp
const char* ssid = "seu-ssid";
const char* password = "sua-senha";
5. Faça o upload do código
Selecione a placa ESP32-C3 em Tools > Board.
Conecte seu ESP32-C3 Mini ao computador.
Faça o upload do código.
Como usar
Após o upload, abra o Serial Monitor para verificar se o ESP32 se conectou ao Wi-Fi e obteve um IP.
Acesse o IP obtido no navegador (ex: http://192.168.0.168).
Visualize as leituras de BPM e SpO2 na página web.
