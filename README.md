# Banco API - Testes de Performance

Repositório contendo scripts de **testes de performance** para a aplicação [Banco API](https://github.com/juliodelimas/banco-api), desenvolvidos em **JavaScript** utilizando o **[k6](https://k6.io/)**.

---

## 📖 Introdução

O objetivo deste projeto é avaliar o desempenho e a escalabilidade da API do banco, medindo métricas como:
- Tempo de resposta
- Taxa de requisições por segundo
- Erros durante carga
- Comportamento sob diferentes cenários de usuários simultâneos

Esses testes permitem identificar gargalos de performance e auxiliar na otimização da aplicação.

---

## 🛠️ Tecnologias utilizadas

- [JavaScript (ES6+)](https://developer.mozilla.org/pt-BR/docs/Web/JavaScript) → Linguagem para os scripts de teste.  
- [k6](https://k6.io/) → Ferramenta open-source para execução de testes de carga e performance.  
- Variáveis de ambiente → Configuração dinâmica do ambiente de teste (ex: 'BASE_URL').  

---

## 📂 Estrutura do repositório

```bash
banco-api-performance/
├── fixtures/           # Dados de entrada para os testes (ex: usuários, payloads)
├── helpers/            # Funções utilitárias reutilizáveis para interação com a API
├── tests/              # Casos de teste organizados por módulo da API
├── utils/              # Funções utilitárias e comuns aos cenários
├── config/             # Arquivo de configuração de variáveis de ambiente
└── README.md           # Este arquivo explica a um usuário como executar o projeto
```

---

## 🎯 Objetivo de cada grupo de arquivos

- **fixtures/** → Dados de entrada para os testes (ex: usuários, payloads).
- **helpers/** → Dados de entrada para os testes (ex: usuários, payloads).
- **tests/** → Dados de entrada para os testes (ex: usuários, payloads).  
- **utils/** → Funções auxiliares que podem ser reutilizadas em diferentes cenários.
- **config/** → Arquivo de configuração de variáveis de ambiente.  
---

## ⚙️ Instalação e Execução

1. **Clone o repositório:**
   ```bash
   git clone https://github.com/brunockutzke/banco-api-performance.git
   cd banco-api-performance
   ```

2. **Configure as Variáveis de Ambiente**
   
   Altere o arquivo `.config.local.json` e defina a URL base da API a ser testada:

   ```json
   {
    "baseUrl": "http://localhost:3000"
   }
   ```

   > Essas variáveis serão usadas dinamicamente nos testes para montar as requisições.

3. **Execute um Teste**

```bash
k6 run tests/login.test.js
```

Certifique-se de passar a variável de ambiente `BASE_URL`, caso não esteja usando um arquivo `config.local.json` ou uma abordagem de carregamento automático:

```bash
k6 run tests/login.test.js -e
BASE_URL=http://localhost:3000
```

4. **Acompanhamento em Tempo Real + Exportação de Relatório**

Você pode ativar o modo dashboard do k6 e exportar o relatório ao final do teste:

```bash
k6_WEB_DASHBOARD=true \
K6_WEB_DASHBOARD_EXPORT=html-report.html \
k6 run tests/login.test.js \
-e BASE_URL=http://localhost:3000 \
```

Após a execução, o relatório estará salvo como `html-report.html`.


📌 Agora você tem um ambiente configurado para rodar diferentes cenários de teste de performance da **Banco API**.

---
