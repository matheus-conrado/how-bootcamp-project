# Projeto de ingestão de dados indicadores socioeconômicos dos países

🚧 Em Construção 🚧

## Proposta

Criar e Estruturar um Data Lake que conterá os dados coletados da API do IBGE referente aos indicadores socioeconômicos dos países (Econimicas, Sociais, População, Redes, etc)

## Motivação

Hoje temos muitos dados referentes as informações socieconomicas entregues na API do IBGE de forma gratuita, mas nem todas as pessoas tem skill tecnico para coletar e analisar esses dados. Pensando nisto esse projeto tem como finalidade agrupar esses dados e de uma maneira mais simplista, organizada, oferecer analises que possam gerar insigths para analistas e cientistas de dados. 

## Métodos

Será utilizado scripts em python para a coleta dos dados na API especificadas, a implantação destes scripts será feita no ambiente em nuvem da AWS por meio de funções Lambda, os dados brutos serão armazenados no formato .json no bucket "bronze_layer" do data lake, estes dados serão carregados pelo Apache Spark para transformação na forma tabular e finalmente serem gravados no formato .parquet no bucket "silver_layer" do data lake. Análises simples com os dados tabulares já poderão ser realizadas com os dados por meio do AWS Athena. Futuramente podem ser construídas métricas que serão servidas na camada "gold_layer" do data lake.

## Objetivo

Os objetivos principais são obter familiaridade e vivência nos processos e ferramentas de engenharia de dados utilizados no mercado bem como demonstrar habilidades nestes, dito isto, entende-se que o processamento dos dados não demanda necessariamente os serviços selecionados.

## Fontes de dados

Dados de indicadores socieconomicos pelo IBGE: Informações sobre os 193 países-membros da Organização das Nações Unidas (ONU). Para esta versão inicial, os identificadores dos países são os definidos pela norma ISO 3166-1 ALPHA-2, que define o identificador do país usando 2 letras. Tais identificadores podem ser consultados na Base de identificadores. Para fins desta API, os países foram organizados de acordo com a metodologia M49 da Organização das Nações Unidas, segundo o qual os países são agrupados em regiões - Equivalente ao que conhecemos como continentes -, sub-regiões e regiões intermediárias, da qual o Brasil é signatário. Para maiores informações, acesse https://unstats.un.org/unsd/methodology/m49/

## Ferramentas

- AWS Lambda para implatação dos scripts de ingestão
- AWS S3 armazenamento dos dados
- AWS Athena para consultas simples
- Apache Spark para processamento dos dados
- Airflow para orquestração de todos os jobs

## Arquitetura
![How_project](https://user-images.githubusercontent.com/65983460/204163326-771312db-4136-4f35-86a0-9d191d818cc0.jpg)
