<p align="center"><img src="assets/logo.png" alt="Health&Med"/></p>

### FIAP - Hackathon 2024 - SOAT4 - Grupo 11 
- Alexandre Mikio Kimura Fukano - **RM 351127** (alexandremkimura@hotmail.com)
- Lucas Proença Renó - **RM 351351** (lucasreno9@gmail.com)
- Matheus Augusto Leme Matiazzo - **RM 351128** (mathmatiazzo@gmail.com)
- Vinicius Carloto Carnelocce - **RM 351126** (viniciuscarloto@gmail.com)

---

### Links úteis
[![Hackathon 2024](https://img.shields.io/badge/Hackathon%20(.pdf)-2024-blue?logo=readthedocs)](/assets/hackathon-soat.pdf)
[![Documentação](https://img.shields.io/badge/Documentação%20Projeto-044464?logo=github)](https://github.com/lucasreno/docs-hackathon/)
<br>
[![Infraestrutura](https://img.shields.io/badge/Infraestrutura-gray?logo=github)](https://github.com/MMatiazzo/infra-hackathon)
[![Microsserviço-Autenticacao](https://img.shields.io/badge/Microsserviço%20Autenticação-gray?logo=github)](https://github.com/MMatiazzo/autenticacao)
[![Microsserviço-Consulta](https://img.shields.io/badge/Microsserviço%20Consulta-gray?logo=github)](https://github.com/MMatiazzo/consulta)


# Infraestrutura

![Infraestrutura](https://github.com/lucasreno/docs-hackathon/blob/15e4fa60634293fdc377a4d9557cbc3e4a6945dd/arquitetura/hackathon-infra.drawio.png?raw=true)

- #### Github Actions
  Nosso CI/CD é feito com Github Actions. Existem 3 workflows configurados:
  - **Terraform Create Cluster Workflow**: Responsável por criar o cluster EKS e realizar as configurações iniciais de rede e segurança.
  - **Terraform Create Database Autenticacao Workflow**: Responsável por criar o banco de dados RDS para o microsserviço de autenticação.
  - **Terraform Create Database Consulta Workflow**: Responsável por criar o banco de dados RDS para o microsserviço de consulta.

  _Todos os workflows são disparados em 3 situações: push, pull_request e dispatch._
     

- #### Serviços AWS
  | Serviço    | Descrição                    |
  |------------|------------------------------|
  | S3         | Storage                      |
  | RDS        | Banco de dados relacional    |
  | SQS        | Fila de mensagens            |
  | ECR        | Registro de contêineres      |
  | EKS        | Kubernetes cluster           |
  | SNS        | Serviço de notificações      |
  | Lambda     | Funções serverless           |
  | Cognito    | Serviço de autenticação      |
  | API Gateway| Gateway de APIs              |

- #### Stack
  | Ferramenta      | Descrição                    |
  |-----------------|------------------------------|
  | Terraform       | Infraestrutura como código   |
  | Helm            | Gerenciador de pacotes       |
  | Docker          | Contêineres                  |
  | Kubernetes      | Orquestrador de contêineres  |
  | Github          | Repositório de código        |
  | Github Actions  | CI/CD                        |
  | Github Secrets  | Variáveis de ambiente do CI  |
