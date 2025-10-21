---

# Knowledge Base: Análise de Custo de Sensores de Silo - C.VALE (Avicultura)

## 1. Contexto do Projeto e Objetivo

* **Projeto Principal:** Digitalização da Avicultura (AgroCenter) - Módulo AgroCenter Expert.
* **Foco Tecnológico:** Sensores de Silo para monitoramento em tempo real de estoque e consumo de ração.
* **Objetivo Estratégico:** Avaliar a viabilidade econômica (CAPEX + OPEX) de diferentes fornecedores de tecnologia IoT (hardware + software), comparando modelos de **Venda/Compra** e **Comodato**.
* **Alinhamento:** Otimização de custos, redução de perdas por falha de manejo e melhoria na logística de abastecimento de ração.

## 2. Propostas de Equipamento e Mensalidades (Custo Inicial e Recorrente)

*Base: Equipamento para 1 aviário (2 silos) e Mensalidade para 1 aviário.*

| EMPRESA | TIPO PROPOSTA | CUSTO EQUIPAMENTO (2 SILOS) | INSTALAÇÃO | CORREÇÃO BASE SILOS | MENSALIDADE (Por Aviário) | MENSALIDADE INTEGRAÇÃO (+100 Aviários) |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| E-AWARE | VENDA | R$ 35.501,62 | R$ 5.473,86 | R$ 5.503,81 | R$ 259,90 | R$ 15.594,00 |
| E-AWARE | COMODATO | ND | ND | ND | ND | ND |
| AGRISOLUS | VENDA | R$ 14.102,00 | R$ 250,00 | - | R$ 50,00 | R$ 3.000,00 |
| AGRISOLUS | COMODATO | - | R$ 3.930,00 | - | R$ 295,00 | R$ 35.400,00 |
| PECSMART | COMPRA | R$ 9.608,00 | R$ 2.093,00 | - | R$ 29,00 | R$ 3.480,00 |
| PECSMART | COMODATO | - | R$ 2.093,00 | - | R$ 375,04 | R$ 22.502,40 |
| TRINOVATI | COMPRA | R$ 14.280,00 | R$ 780,23 | - | R$ 85,00 | R$ 10.200,00 |
| TRINOVATI | COMODATO | - | R$ 0,00 | - | R$ 349,02 | R$ 41.882,40 |

## 3. Análise de Custo Total (5 Anos) e Impacto Zootécnico

*Base: Projeção de custos considerando 5 anos de operação (CAPEX + OPEX).*

| EMPRESA – TIPO PROPOSTA | CUSTO TOTAL 5 ANOS (Por Aviário) | CUSTO TOTAL 5 ANOS (Integração) | CUSTO POR CICLO (Integração) | CUSTO POR CICLO (Por Aviário) | % CUSTO RAÇÃO |
| :---: | :---: | :---: | :---: | :---: | :---: |
| E-AWARE - VENDA | R$ 62.073,29 | R$ 68.280.619,00 | R$ 2.276.020,63 | R$ 2.069,11 | 1,04% |
| AGRISOLUS - VENDA | R$ 17.352,00 | R$ 19.087.200,00 | R$ 636.240,00 | R$ 578,40 | 0,29% |
| AGRISOLUS - COMODATO | R$ 21.630,00 | R$ 23.793.000,00 | R$ 793.100,00 | R$ 721,00 | 0,36% |
| PECSMART – VENDA \* | R$ 13.441,00 | R$ 14.785.100,00 | R$ 492.836,67 | R$ 448,03 | **0,23%** |
| PECSMART – COMODATO \* | R$ 24.595,40 | R$ 27.054.940,00 | R$ 901.831,33 | R$ 819,85 | 0,41% |
| TRINOVATI - VENDA | R$ 20.160,23 | R$ 22.176.253,00 | R$ 739.208,43 | R$ 672,01 | 0,34% |
| TRINOVATI - COMODATO | R$ 20.941,20 | R$ 23.035.320,00 | R$ 767.844,00 | R$ 698,04 | 0,35% |

## 4. Conclusões e Destaques Estratégicos

1.  **Menor Custo Relativo (Impacto Zootécnico):** A **PecSmart (Venda)** apresenta o menor impacto no custo da ração (0,23%), indicando ser a opção mais competitiva em preço.
2.  **Menor Custo Total (5 Anos):** A **PecSmart (Venda)** também oferece o menor CAPEX + OPEX em 5 anos por aviário (R$ 13.441,00).
3.  **Opção de Baixo Custo (Alinhamento com Open-Source):** A modalidade **VENDA** em geral, e especificamente as propostas da **PecSmart** e **Agrisoulus**, alinham-se ao seu interesse por soluções **open-source** e seu projeto de desenvolver sensores de **baixo custo** com o Senai, pois o CAPEX é menor.
4.  **Custo Mais Alto (Justificativa):** A **E-Aware** (fornecedora do AgroCenter) tem o custo mais elevado em todas as métricas, refletindo, provavelmente, a profundidade da integração nativa com a plataforma AgroCenter, o que pode justificar o preço pela simplificação da governança de dados.

## 5. Próximos Passos (Sugestões Proativas)

* **ROI Simplificado:** Desenvolver um modelo em Excel (DAX/VBA) ou Python/Streamlit que calcule o ROI, comparando o *Custo por Ciclo* (coluna 4) com a economia potencial gerada (ex: redução de 0,5% nas perdas de ração, melhoria de 1% na CA, etc.).
* **Avaliação Técnica:** Comparar as tecnologias de sensor utilizadas por PecSmart e Agrisolus com a tecnologia **Binconnect (Nanolike)** que será testada no Matrizeiro 2, focando em precisão e durabilidade em ambientes desafiadores.
* **Agente de IA:** Utilizar este Knowledge Base no seu projeto de **Construção de Agentes de IA com Docker** (RAG), permitindo que o agente responda perguntas complexas como: *"Qual o custo total por ciclo do sensor de silo de menor impacto percentual no custo da ração?"* (Resposta: R$ 448,03 da PecSmart/Venda).
