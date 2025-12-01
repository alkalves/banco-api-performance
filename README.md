# Testes de performance do banco com k6

## 📝 Introdução

Este repositório contém scripts e cenários de testes de performance
desenvolvidos em **JavaScript** utilizando o **k6**, com o objetivo de
avaliar e monitorar o desempenho da API do projeto [Banco API](https://github.com/juliodelimas/banco-api).

## 🧰 Tecnologias utilizadas

-   **k6** -- Ferramenta para testes de carga e performance.
-   **JavaScript** -- Linguagem utilizada na criação dos scripts.
-   **Node.js** -- Utilizado para gerenciamento de dependências e
    utilidades auxiliares.
-   **GJSON** -– Para extração de dados em respostas JSON.
-   Variáveis de ambiente para configuração dinâmica (ex: BASE_URL).

## 📁 Estrutura do repositório

    ├── fixtures/             # Dados de entrada para os testes
    ├── helpers/              # Funções utilitárias reutilizáveis para interação com a API
    ├── tests/                # Casos de teste organizados por módulo da API
    ├── config/               # Arquivos de configuração de variáveis de ambiente
    ├── utils/                # Funções utilitárias reutilizáveis
    └── README.me             # Documentação do projeto

## 🎯 Objetivo de cada grupo de arquivos

-   **fixtures/**: Dados de entrada para os testes.
-   **helpers/**: Funções utilitárias reutilizáveis para interação com a API.
-   **tests/**: Casos de teste organizados por módulo da API.
-   **config/**: Arquivos de configuração de variáveis de ambiente.
-   **utils/**: Funções utilitárias reutilizáveis.

## 🚀 Instalação e Execução do Projeto

### 1. Clonar o repositório

    git clone https://github.com/alkalves/banco-api-performance

### 2. Instalar dependências

Execute o comando para instalar as dependências do projeto:

    npm install

### 3. Variáveis de ambiente necessárias

Altere o arquivo `config.local.json` e defina a url base da API a ser testada:

```json
{
    "baseUrl": "http://localhost:3000"
}
```

### 4. Executando os testes com k6

#### Execução simples:

    k6 run tests/login.test.js 

#### Execução com dashboard em tempo real:

    K6_WEB_DASHBOARD=true k6 run tests/login.test.js

#### Execução com exportação de relatório:

    K6_WEB_DASHBOARD=true K6_WEB_DASHBOARD_EXPORT=html-report.html k6 run tests/login.test.js

Após a execução, o relatório será salvo na pasta `reports/`.
