# Fundamentos de Internet das Coisas (IoT)
## 📌 Introdução


A Internet das Coisas (IoT — Internet of Things) representa a conexão de dispositivos físicos à internet, permitindo coleta, troca e análise de dados em tempo real. Sensores, atuadores, microcontroladores e sistemas inteligentes trabalham juntos para automatizar processos, monitorar ambientes e apoiar decisões.

Exemplos de aplicações IoT incluem:



Casas inteligentes

Agricultura de precisão

Cidades inteligentes

Indústria 4.0

Saúde conectada

Monitoramento ambiental

🏗️ Arquitetura em Três Camadas

A arquitetura clássica de sistemas IoT é dividida em três camadas principais:

## 1️⃣ Camada de Percepção (Hardware)

A camada de percepção é responsável por interagir diretamente com o mundo físico.

Ela coleta informações do ambiente através de sensores e executa ações utilizando atuadores.

## 🔹 Componentes principais
Sensores de temperatura
Sensores de umidade
Sensores de presença
Câmeras
GPS
Atuadores (motores, relés, LEDs etc.)


## 🔹 Funções
Captura de dados físicos
Conversão de sinais analógicos em digitais
Execução de comandos físicos


## 🔹 Exemplo prático

Um sensor de temperatura mede o ambiente e envia os dados para um microcontrolador como um ESP32 ou Arduino.

## 2️⃣ Camada de Rede (Conectividade)

A camada de rede é responsável pela transmissão dos dados entre dispositivos, servidores e aplicações.

Ela garante que as informações coletadas pelos sensores cheguem ao destino correto.

## 🔹 Tecnologias e redes utilizadas
Wi-Fi
Bluetooth Low Energy (BLE)
Zigbee
LoRaWAN
4G/5G
Ethernet


## 🔹 Funções
Comunicação entre dispositivos
Transporte de dados
Segurança na transmissão
Integração com serviços em nuvem


## 🔹 Protocolos comuns
MQTT
HTTP/REST
CoAP


## 3️⃣ Camada de Aplicação

A camada de aplicação é onde os dados são processados, armazenados e apresentados ao usuário final.

Ela transforma dados brutos em informações úteis.

## 🔹 Funções
Visualização de dashboards
Armazenamento em banco de dados
Processamento em nuvem
Inteligência artificial e análise de dados
Automação


## 🔹 Exemplos de aplicações
Aplicativos móveis
Sistemas web
Plataformas em nuvem
Sistemas de monitoramento industrial


## 🔹 Exemplo prático

Um dashboard web exibe gráficos de temperatura em tempo real e envia alertas caso o valor ultrapasse limites definidos.

📡 Protocolos de Comunicação em IoT

Os protocolos de comunicação são essenciais para garantir troca eficiente de dados entre dispositivos IoT.

📊 Tabela Comparativa
Protocolo	Modelo	Consumo	Velocidade	Uso Principal	Vantagens	Desvantagens
MQTT	Publish/Subscribe	Baixo	Alta	Sensores e telemetria	Leve, eficiente e ideal para IoT	Necessita broker
HTTP (REST)	Cliente-Servidor	Médio/Alto	Média	APIs web e integração	Simples e amplamente utilizado	Mais pesado para dispositivos limitados
CoAP	Cliente-Servidor	Muito baixo	Alta	Dispositivos restritos	Baixo consumo e eficiente	Menor suporte que HTTP


## 🔹 MQTT

O MQTT (Message Queuing Telemetry Transport) é um protocolo leve baseado no modelo Publish/Subscribe.

## Características
Baixo consumo de banda
Ideal para dispositivos limitados
Comunicação assíncrona
Muito utilizado em automação e sensores
Funcionamento
Publisher envia mensagens
Broker gerencia comunicação
Subscriber recebe mensagens


## 🔹 HTTP (REST)

O HTTP é um dos protocolos mais utilizados na internet e também aparece em aplicações IoT.

Características
Comunicação baseada em requisições
Fácil integração com APIs
Compatível com aplicações web
Limitações em IoT
Alto overhead
Maior consumo energético
Menos eficiente em redes instáveis


## 🔹 CoAP

O CoAP (Constrained Application Protocol) foi criado especificamente para dispositivos restritos.

## Características
Baseado em UDP
Muito leve
Baixo consumo energético
Ideal para sensores simples
Vantagens
Excelente para redes com baixa largura de banda
Menor latência

🧠 Digital Twin

## 📌 O que é Digital Twin?

Digital Twin (Gêmeo Digital) é uma representação virtual de um objeto, sistema ou processo físico.

Ele recebe dados em tempo real do dispositivo físico através de sensores IoT e replica digitalmente seu comportamento.

## 🔹 Como funciona
Sensores coletam dados do objeto físico
Os dados são enviados para a nuvem
O modelo digital é atualizado em tempo real
O sistema analisa informações e prevê comportamentos
🔹 Aplicações
🏭 Indústria 4.0

Monitoramento de máquinas industriais para prever falhas.

🚗 Veículos Inteligentes

Simulação do desempenho de automóveis em tempo real.

🏙️ Cidades Inteligentes

Monitoramento de trânsito, iluminação e consumo energético.

🏥 Saúde

Acompanhamento remoto de equipamentos médicos.

## 🔹 Benefícios
Manutenção preditiva
Redução de custos
Melhor tomada de decisão
Simulações em tempo real
Maior eficiência operacional
🚀 Conclusão

A Internet das Coisas conecta o mundo físico ao digital através de sensores, redes e aplicações inteligentes.

Com a arquitetura em três camadas, protocolos de comunicação eficientes e tecnologias como Digital Twin, a IoT se torna fundamental para automação, análise de dados e transformação digital em diversos setores.

📚 Referências

MQTT.org

IETF CoAP Documentation

IBM Cloud IoT

AWS IoT Core

Cisco IoT Reference Model
---

# Sistema de Monitoramento de Nível de Água

## 📌 Objetivo
Projetar um sistema IoT capaz de monitorar o nível de água utilizando sensor ultrassônico, microcontrolador ESP32 e comunicação em nuvem.

---

# 🏗️ Arquitetura do Sistema

## Fluxo de Dados

```text
[Sensor Ultrassônico HC-SR04]
        │
        │ Sinal Digital (Trigger/Echo)
        ▼
[ESP32]
        │
        │ Wi-Fi + MQTT/HTTP
        ▼
[Roteador Wi-Fi]
        │
        │ Internet (TCP/IP)
        ▼
[Servidor/Nuvem]
(Banco de Dados + Dashboard + Alertas)
```

---

# 🔍 Descrição da Arquitetura

## 1. Sensor Ultrassônico HC-SR04
Responsável por medir a distância entre o sensor e a superfície da água utilizando ondas ultrassônicas.

### Comunicação
- Sinal Digital
- Pinos Trigger e Echo

---

## 2. ESP32
Microcontrolador responsável por:
- Ler os dados do sensor
- Processar as medições
- Enviar informações para a nuvem

### Comunicação
- Wi-Fi
- MQTT ou HTTP

---

## 3. Roteador Wi-Fi
Responsável por conectar o ESP32 à internet.

### Protocolos
- IEEE 802.11 b/g/n
- TCP/IP

---

## 4. Servidor/Nuvem
Responsável por:
- Receber os dados do ESP32
- Armazenar informações
- Exibir dashboard em tempo real
- Gerar alertas

### Tecnologias possíveis
- AWS
- Firebase
- ThingsBoard
- Google Cloud

---

# 📡 Tecnologias Utilizadas

| Camada | Tecnologia |
|---|---|
| Sensor | HC-SR04 |
| Microcontrolador | ESP32 |
| Comunicação | Wi-Fi |
| Protocolo IoT | MQTT |
| Backend | Node.js / Python |
| Banco de Dados | Firebase / MySQL |
| Dashboard | Grafana / ThingsBoard |

---

# 📊 Exemplo de Expansão

```text
Servidor → Banco de Dados → Dashboard → Usuário
```

---

# 🚀 Possíveis Melhorias
- Alertas por Telegram ou Email
- Dashboard Mobile
- Criptografia TLS
- Armazenamento em nuvem
- Histórico de medições
