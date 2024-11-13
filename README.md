# Projeto de Monitoramento Agrícola Inteligente

Este projeto visa criar um sistema inteligente de monitoramento agrícola utilizando o microcontrolador ESP32 e diversos sensores para coletar dados ambientais e otimizar o uso de recursos na agricultura. O sistema simulado monitora temperatura, umidade, nível de água, movimento e intensidade de luz para automatizar o controle de irrigação e segurança em uma área agrícola.

## Objetivo do Projeto

Desenvolver um sistema capaz de:

1. Monitorar condições ambientais em tempo real.
2. Controlar automaticamente a irrigação com base em dados coletados.
3. Alertar sobre movimentos suspeitos para proteger o ambiente.
4. Ajustar a irrigação conforme a intensidade da luz solar.

## Sensores Utilizados

1. **DHT22**: Medição de temperatura e umidade.
2. **HC-SR04**: Monitoramento do nível de água em reservatórios.
3. **PIR**: Detecção de movimento para segurança e monitoramento.
4. **LDR**: Medição da intensidade da luz solar para ajuste na irrigação.

## Funcionalidades

1. **Monitoramento Climático**: Com o sensor DHT22, o sistema coleta dados de temperatura e umidade, otimizando a irrigação com base nas condições.
2. **Controle de Irrigação Automatizado**: O sensor ultrassônico HC-SR04 monitora o nível de água, garantindo que a irrigação ocorra apenas quando necessário.
3. **Detecção de Presença**: O sensor PIR detecta movimento, auxiliando na segurança do ambiente.
4. **Ajuste de Irrigação com Base na Luminosidade**: O sensor LDR ajusta a quantidade de água com base na intensidade da luz solar.

## Estrutura do Repositório

- **/src**: Códigos-fonte do projeto.
- **/docs**: Documentação do projeto, incluindo a descrição do sistema e dos sensores.
- **/tests**: Testes manuais e automatizados para validar o sistema.

## Configuração e Execução do Projeto

### Simulação
![Print do projeto pronto no wokwi](https://i.imgur.com/Er2WTkg.png)
Para simular o projeto, utilize o [Wokwi](https://wokwi.com/projects/413986707065798657) com o ESP32:

1. Acesse o Wokwi e crie um novo projeto com ESP32.
2. Conecte os sensores DHT22, HC-SR04, PIR e LDR conforme o diagrama de circuito.
3. Cole o código-fonte em `src/` para rodar a simulação.
4. Use o Monitor Serial do Wokwi para visualizar as leituras dos sensores e o funcionamento do sistema.

### Banco de Dados

O projeto armazena dados em um banco de dados SQLite local (`sensores.db`). A estrutura da tabela `dados_sensores` foi criada para registrar:

- Nutriente P
- Nutriente K
- pH
- Umidade
- Estado da irrigação (`ATIVADA` ou `DESATIVADA`)
- Data e hora da leitura

### Instalação

Certifique-se de que você tem o Python e o SQLite instalados. Instale também o `sqlite3` para conectar ao banco de dados.

## Como Usar

1. Execute o código principal para iniciar a coleta e o armazenamento de dados.
2. Visualize os dados no banco com a função `ler_dados()` que exibe todas as leituras armazenadas.

## Estrutura do Banco de Dados

A tabela `dados_sensores` possui a seguinte estrutura:

| Campo          | Tipo     | Descrição                                           |
|----------------|----------|-----------------------------------------------------|
| id             | INTEGER  | Identificador único da leitura                      |
| nutriente_p    | INTEGER  | Nível de fósforo (P)                                |
| nutriente_k    | INTEGER  | Nível de potássio (K)                               |
| ph             | REAL     | Medição de pH do solo                               |
| umidade        | REAL     | Umidade medida pelo sensor                          |
| irrigacao_ativa| TEXT     | Estado da irrigação (`ATIVADA` ou `DESATIVADA`)     |
| data_hora      | TIMESTAMP| Data e hora da leitura, com padrão automático       |

## Testes

No repositório, há uma pasta de testes que inclui:

1. **Testes manuais**: para validação do funcionamento dos sensores e da conexão do banco.
2. **Testes de leitura**: verificando a recuperação correta dos dados no banco.

## Diagrama de Circuito

O circuito completo, incluindo a conexão de cada sensor ao ESP32, está documentado na pasta `/docs` e deve ser seguido para a simulação no Wokwi.

## Commits e Controle de Versão

- **Branch**: O desenvolvimento ocorre na branch `develop` antes de integrar à `main`.
- **Commits**: São feitos frequentemente, com descrições claras.
- **Pull Request**: Cada nova feature é enviada para revisão por meio de um PR.

## Instruções de Entrega

1. Poste o link do GitHub no portal do aluno antes do prazo final.
2. Não altere mais o repositório após a entrega.
3. Revise o horário de commits no GitHub para evitar penalizações.

## Prints e Demonstração

Na pasta `/docs`, inclua prints do Monitor Serial mostrando a coleta de dados e o funcionamento do sistema.
