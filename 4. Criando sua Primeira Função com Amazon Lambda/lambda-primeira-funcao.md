# ⚡ Criando sua Primeira Função com Amazon Lambda  

Este documento registra a prática realizada no curso **Criando sua Primeira Função com Amazon Lambda**, incluindo a criação, configuração e execução de uma função Lambda com integração ao S3.  

---

## ✅ O que foi feito  
- Criação da função **Lambda FunctionHelloWorld** em Python.  
- Configuração do código para receber parâmetros via **event** e imprimir valores (`key1`, `key2`, `key3`).  
- Criação e execução de **eventos de teste** para validar a função.  
- Integração da função Lambda com o **Amazon S3** para executar automaticamente quando um objeto `.csv` fosse criado.  
- Visualização e análise dos **logs no CloudWatch**.  

---

## 🛠️ Ferramentas utilizadas  
- **AWS Lambda** – execução de código serverless  
- **Amazon S3** – armazenamento e gatilho da função  
- **Amazon CloudWatch** – monitoramento e logs  
- **Python 3.12** – linguagem utilizada na função  

---

## 📷 Prints / Galeria  

### 🔹 Teste da Função Lambda  
<img width="1913" height="907" alt="teste lambda" src="https://github.com/user-attachments/assets/c6e84bbd-c1e7-4173-b9ea-4094a303472e" />

### 🔹 Trigger configurado no S3  
<img width="1920" height="1080" alt="trigger" src="https://github.com/user-attachments/assets/692a9a41-e60a-414c-a673-01b14f59ea25" />

### 🔹 Logs no CloudWatch  
<img width="1920" height="904" alt="logs" src="https://github.com/user-attachments/assets/33d5efc2-4fbb-442c-a5cf-1d20525bd329" />

---

## 📚 Aprendizados  
- Criar e configurar uma **função Lambda** do zero.  
- Entender como passar **eventos de teste** em JSON.  
- Integrar Lambda com **triggers do S3**.  
- Monitorar execuções e erros com **CloudWatch**.  


