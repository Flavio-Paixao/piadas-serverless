# 🎲 Piadas de Programador — AWS Serverless

> API Serverless de piadas de programador desenvolvida com Python e hospedada inteiramente na AWS — sem servidor, sem limites.

🔗 **[Ver projeto ao vivo](http://piadas-serveless-flavio.s3-website-sa-east-1.amazonaws.com/)**

---

## 🏗️ Arquitetura Serverless

```
Usuário → API Gateway → Lambda (Python) → DynamoDB
```

```
┌─────────────┐     ┌──────────────────┐     ┌─────────────────┐     ┌─────────────┐
│  Frontend   │────▶│   API Gateway    │────▶│ Lambda (Python) │────▶│  DynamoDB   │
│  (S3)       │     │  HTTP API        │     │ piadas-function │     │ tabela:     │
└─────────────┘     └──────────────────┘     └─────────────────┘     │ piadas      │
                                                                       └─────────────┘
```

---

## ☁️ Serviços AWS Utilizados

| Serviço | Função |
|---|---|
| **AWS Lambda** | Função Python que busca piada aleatória no DynamoDB |
| **API Gateway** | Expõe a Lambda como endpoint HTTP público |
| **DynamoDB** | Banco NoSQL que armazena as piadas |
| **Amazon S3** | Hospedagem do frontend estático |
| **IAM** | Permissões de acesso entre os serviços |

- **Região:** `sa-east-1` (São Paulo)
- **Runtime:** Python 3.12
- **Tipo de API:** HTTP API

---

## 🚀 Como funciona

1. Usuário acessa o frontend hospedado no S3
2. Clica em **"Nova Piada"**
3. O JavaScript faz uma requisição GET para o API Gateway
4. O API Gateway invoca a função Lambda
5. A Lambda busca um item aleatório no DynamoDB
6. Retorna a piada em JSON para o frontend
7. O frontend exibe a piada com animação

---

## 📡 Endpoint da API

```
GET https://hzhictul0h.execute-api.sa-east-1.amazonaws.com/piada
```

**Resposta:**
```json
{
  "id": "3",
  "piada": "Qual o animal favorito do programador? O bug!",
  "categoria": "programacao"
}
```

---

## 💡 Diferenciais do projeto

- **100% Serverless** — sem servidor para gerenciar, escala automaticamente
- **Custo zero** — dentro do Free Tier da AWS
- **Alta disponibilidade** — AWS garante uptime automaticamente
- **Baixa latência** — Lambda executa em milissegundos

---

## 📁 Estrutura

```
piadas-serverless/
├── index.html          # Frontend com design dark
└── README.md
```

---

## 👨‍💻 Sobre

**Flávio da Paixão Nunes** — Desenvolvedor Backend Python | AWS Cloud  
Estudante de Engenharia de Software (Ampli/Anhanguera) — 2º ano  
Santos, São Paulo - SP

[![LinkedIn](https://img.shields.io/badge/LinkedIn-flaviopx-blue?style=flat&logo=linkedin)](https://www.linkedin.com/in/flaviopx)
[![GitHub](https://img.shields.io/badge/GitHub-Flavio--Paixao-black?style=flat&logo=github)](https://github.com/Flavio-Paixao)
[![Portfolio](https://img.shields.io/badge/Portf%C3%B3lio-AWS-orange?style=flat&logo=amazonaws)](https://projeto-aws-681892816208-sa-east-1-an.s3.sa-east-1.amazonaws.com/index.html)

---

## 🚀 Stack

![AWS Lambda](https://img.shields.io/badge/AWS_Lambda-Python-orange?style=flat&logo=awslambda)
![API Gateway](https://img.shields.io/badge/API_Gateway-HTTP-orange?style=flat&logo=amazonaws)
![DynamoDB](https://img.shields.io/badge/DynamoDB-NoSQL-blue?style=flat&logo=amazondynamodb)
![S3](https://img.shields.io/badge/Amazon_S3-Frontend-orange?style=flat&logo=amazons3)
