# ☁️ Arquitetura AWS - API Gateway, Lambda, EC2, S3, RDS e CloudWatch.
Este projeto descreve uma arquitetura moderna na AWS, utilizando recursos **serverless** e de **computação escalável** para processor requisições, armazenar dados e monitorar a aplicação.

---
## 🚀 Fluxo da Arquitetura 

1. **Usuário (ou Aplicação Cliente) 👤**
   Envia uma **requisição HTTP/HTTPS** para o **API Gateway**.
   
2. **API Gateway 🌐**
      - Atua como **porta de entrada** da aplicação.
      - Encaminha a requisição para a função **AWS Lambda**.
  
3. **Lambda ⚡ (Serverless Function)**
   - Executa a **lógica de negócio**.
   - Pode realizar duas ações principais:
      - Gravar dados processados diretamente no **S3**
      - Acionar o **EC2** caso precise de **tarefas mais pesadas**.
    
4. **EC2 🖥️**
   - Roda a aplicação principal.
   - Possui armazenamento persistente via **EBS (Elastic Block Store)**.
  
5. **S3 🗂️**
   - Armazena arquivos, dados não estruturados e resultados processados pelo **Lambda**.

6. **RDS 🧵**
   - Banco de dados relacional gerenciado (MySQL/PostgreSQL).
   - Utilizado para persistir dados **estruturados**.
   - Possui **snapshots automáticos** para backup e alta disponibilidade.
  
7. **CloudWatch 📊**
   - Monitora lods, métricas e eventos de toda a arquitetura
   - Garante **obsrvabilidade** e alertas de performance.

---

## 🔀 Resumo dos Fluxos de Comunicação

- **Usuário → API Gateway → Lambda**
- **Lambda → S3** (grava dados processados)
- **Lmabda → EC2 → EBS** (tarefas pesadas com armazenamento persistente)
- *Lambda → RDS** (persistência de dados estruturados)
- **CloudWatch** monitora **tudo** (Lambda, EC2, API Gateway, RDS).


## 🛠️ Tecnologias Utilizadas 

- **Amazon API Gateway** → Entrada de requisições
- **AWS Lambda** → Funções serverless
- **Amazon EC2 + EBS** →  Computação escalável com armazenamento persistente
- **Amazon RDS** → Banco de dados relacional gerenciado
- **Amazon CloudWatch** → Monitoramento e métricas


✨ **Autora** 
👩🏻‍💻 Lauane Correia 
Estudante de Comércio Exterior e apaixonada por tecnologia ☁️

