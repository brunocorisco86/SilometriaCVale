# Premissas para a construção de um bom sensor de silo - por Bruno Conter
---

# Knowledge Base: Premissas Estratégicas para Sensores de Silo - V2.0

## 1. Contexto e Premissa Fundamental

* **Projeto:** Desenvolvimento/Avaliação de Sensores de Silo para Avicultura de Precisão (AgroCenter Expert).
* **Premissa Central:** Equilíbrio entre Custo, Acuracidade e Facilidade de Instalação (Equilíbrio Custo/Acuracidade/Instalação).
* **Objetivo:** Viabilizar o CAPEX, escalar a tecnologia e garantir um **Uptime Alto** do sistema.

## 2. Tecnologias de Sensoriamento (Requisitos)

O KB prioriza a abordagem **Sem Contato** devido à natureza da ração e operacionalidade.

### 2.1. Sem Contato (Prioridade)
* **Time-of-Flight (ToF):** Tecnologia ideal.
    * **Princípio:** Mede o tempo de pulso de luz ou onda (Laser/Rádio).
    * **Prós:** Imune a fumaça, poeira e vapor (condições comuns em aviários).
    * **Exemplos:** LiDAR (Laser - Benewake, BinSentry) ou Radar (Onda de Rádio - Vega, Emerson Rosemount).
* **Ultrassom:**
    * **Prós:** Baixo custo, adequado para Protótipos/PoC.
    * **Contras:** Alta sensibilidade a temperatura, umidade e poeira.

### 2.2. Com Contato
* **Células de Carga (Peso):** Oferece **precisão extrema**, mas exige mudanças estruturais e tem **alto custo**.
* **Microcélulas (Tensão):** Solução de instalação intermediária ("plug and play").

## 3. Arquitetura de Comunicação e Energia

### 3.1. Comunicação (Resiliência de Sinal)
* **LoRaWAN:** Preferencial. Prós: **Baixo consumo**, **Longo alcance** e **Sem custo mensal**.
* **NB-IoT:** Contras: **Custo recorrente** e **Baixa cobertura em áreas rurais no Brasil** (considerado um grande risco).
* **Protocolos:** **MQTT** (leve, ideal para IoT e Open-Source) e compatibilidade com Modbus/4-20mA (legado).

### 3.2. Fonte de Energia (Resiliência Energética)
* **Opções:** Painel Solar + Bateria de Lítio (recarregável) ou Energia Elétrica (explorar **NR10 ABNT**).
* **Gestão:** Uso de Gerenciamento Inteligente (modo "sleep" para economia).

## 4. Dados e Confiabilidade do Sistema

### 4.1. Armazenamento e Envio
* **Buffer Local:** Memória Flash (SD Card) para armazenar dados por no mínimo 3 dias (Confiabilidade/Disponibilidade).
* **Taxa de Envio:** Máximo de 5 minutos, Mínimo de 30 minutos a cada leitura.
* **Precisão:** Requisito **Mínimo de 95% de acuracidade** sobre as notas fiscais de entrega.

### 4.2. Formato de Dados (JSON Estruturado)
O formato **JSON** é obrigatório (leve e flexível) e deve conter:
| Categoria | Metadados Chave | Objetivo |
| :---: | :---: | :---: |
| **Identificação** | `id_silo`, `id_sensor`, `hash_firmware` | Rastreabilidade do hardware e software. |
| **Tempo** | `timestamp` (UTC), `time_to_transmit` | Padronização e monitoramento da latência. |
| **Dispositivo** | `bateria` (%), `temperatura_interna`, `sinal_rssi` | **Heartbeat** e Diagnóstico Integrado (Saúde do Sistema). |
| **Medição** | `nivel_produto`, `peso_produto` | Dados brutos da leitura. |
| **Negócio/Contexto** | `evento_contexto`, `id_lote` | Suporte a **Edge Computing** (eventos) e rastreabilidade do produto. |
| **Segurança/Rastreabilidade** | **Geolocalização** (no sensor ou cadastro) | Garante a acuracidade no dashboard e, com o **Cadastro do Produtor no Hardware**, permite o registro via **Blockchain** (prevenção contra furto/roubo). |

## 5. Viabilidade Econômica e Escalabilidade

### 5.1. Custo e Garantia
* **Custo Máximo de Aquisição:** R$ 10.000,00 por aviário (considerando 2 Silos / 2 Sensores).
* **Duração/Garantia Mínima:** 5 anos.
* **Custo Recorrente:** A meta é ser **Sem custo recorrente** (favorece LoRaWAN).

### 5.2. Modelo de Negócio (ROI)
Para maximizar o Retorno sobre o Investimento (ROI), explorar opções como:
* Opção 1: Pagamento de **1 centavo/ave** (se os dados forem completos).
* Opção 2: R$ 0,14 por metro quadrado (pago ao produtor).
* **Canais de Venda:** Venda pela rede de lojas de acessórios da C.Vale ou venda direta com incentivo fiscal.

## 6. Edge Computing e Automação (Inteligência Local)

* **Capacidades de Detecção (Baseadas em Eventos):** Carregamento do silo, Período sem consumo ("flat"), Silo vazio e Chegada de caminhão.
* **Recursos de Hardware (DIY):** Explorar Reconhecimento de Som (INMP441) e Detecção de Objetos/Presença Humana (ESP32 Cam, LD2420) para automação local.
* **Automação:** Uso de **Node-RED** para automações no local e suporte a diversos frameworks.
* **Atuadores:** Uso de Relés, como o acionamento de luz para indicar que o silo está pronto para descarga.
