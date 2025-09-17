# 🔄 Prática DIO: Workflow de Processamento de Dados com AWS Step Functions

## 📋 Descrição da Prática
Esta prática tem como objetivo consolidar os **workflows automatizados** utilizando o **AWS Step Functions**.  
Você irá criar, configurar e executar um workflow que processa arquivos armazenados em um bucket S3, utilizando o padrão **Distributed Map** para execução paralela e agregação de resultados com AWS Lambda.

---

## 🎯 Objetivos de Aprendizagem
Ao concluir esta prática, você será capaz de:  

- 💡 Aplicar conceitos de Step Functions em um ambiente prático.  
- 📝 Documentar processos técnicos de forma clara e organizada.  
- 🔗 Integrar serviços AWS (Step Functions, Lambda e S3) em um workflow funcional.  
- 📊 Monitorar e depurar execuções usando Amazon CloudWatch.  
- ⚙️ Explorar o padrão **Distributed Map** para processamentos paralelos.
---


## 🏗️ Passo a Passo da Prática

O workflow implementado segue o modelo **"Process data in an Amazon S3 bucket with Distributed Map"**, ideal para processamento paralelo de arquivos.  
Documentação oficial da AWS: [Distributed Map Sample](https://docs.aws.amazon.com/step-functions/latest/dg/sample-dist-map-s3data-process.html)

O processo consiste nas seguintes etapas:

### 1️⃣ Escolha do Modelo Distributed Map
O primeiro passo é selecionar o modelo de **Mapa Distribuído** no Step Functions, permitindo processar múltiplos arquivos de forma paralela.
<img width="1920" height="1080" alt="modelo" src="https://github.com/user-attachments/assets/c69eb74b-6a37-4d9b-b6d5-556736a54a31" />
---

### 2️⃣ Design do Workflow
O workflow foi projetado para gerenciar o processamento de arquivos de forma organizada, com as seguintes etapas:  

- 📥 **Entrada de Dados (S3):** Lista de arquivos a serem processados.  
- 🔄 **Distributed Map:** Itera sobre cada arquivo individualmente.  
- ⚡ **Função Lambda de Processamento:** Executa a transformação/análise dos dados de cada arquivo.  
- 🗂️ **Lambda Reducer:** Consolida os resultados parciais em um resultado final.  
- 📤 **Saída de Dados (S3):** Armazena o resultado final no bucket de saída.

<img width="1920" height="1080" alt="design" src="https://github.com/user-attachments/assets/372d1962-c83b-4b23-9510-c464c780c1dd" />
---

### 3️⃣ Alteração do Input para `year: 2025`
Antes de iniciar a execução, o **input** do workflow foi modificado para incluir o parâmetro `year: 2025`. Isso permite simular o processamento de dados referentes a esse ano específico.
<img width="1920" height="1080" alt="input" src="https://github.com/user-attachments/assets/b0f1091d-2b4b-4395-aba8-2d3a73c29ae3" />
---

### 4️⃣ Função Lambda Criada
A função Lambda é responsável por processar cada arquivo individualmente. Pode incluir operações como leitura de CSV/JSON, transformação de dados, validação ou enriquecimento das informações.
<img width="1920" height="1080" alt="lambda" src="https://github.com/user-attachments/assets/1bea96c2-6941-4373-a231-bacd313445ec" />
---

### 5️⃣ Buckets S3 Criados
Dois buckets foram utilizados:  

- 📥 **Bucket de Entrada:** Armazena os arquivos a serem processados.  
- 📤 **Bucket de Saída:** Recebe os resultados consolidados após o processamento.
<img width="1920" height="1080" alt="bucket" src="https://github.com/user-attachments/assets/a75e6c12-ed13-46a3-bec2-da8c5bc08179" />
---
### 6️⃣ Grupo de Logs no CloudWatch
O Step Functions foi integrado ao **Amazon CloudWatch**, permitindo monitorar cada execução, identificar falhas e depurar o workflow. Todos os eventos do workflow são registrados aqui.

<img width="1920" height="1080" alt="logs" src="https://github.com/user-attachments/assets/2c204edb-e598-4beb-b61d-ac51b5051876" />

---

## 🔍 Detalhes do Processo

1. 📂 **Leitura de Arquivos:** O workflow inicia lendo todos os arquivos do bucket S3 de entrada.  
2. 🔄 **Distribuição das Tarefas:** O estado **Distributed Map** distribui cada arquivo para execução paralela.  
3. ⚡ **Processamento Individual:** Cada arquivo é processado por uma função Lambda.  
4. 🗂️ **Agregação de Resultados:** Após processar todos os arquivos, a **Reducer Function** consolida os dados em um único arquivo de saída.  
5. 📤 **Armazenamento Final:** O arquivo final é salvo no bucket S3 de saída, completando o workflow.  

---

## 🏁 Resultados e Conclusão
O workflow foi executado com sucesso, demonstrando a **eficiência do padrão Distributed Map** para processamentos paralelos em larga escala.  

- ✅ Os arquivos foram processados corretamente.  
- 📂 O resultado final foi consolidado e armazenado no bucket de saída.  
- 📊 O CloudWatch permitiu acompanhar cada etapa e identificar possíveis erros.  
---

**Conclusão:**  
Esta prática reforçou o entendimento da orquestração de workflows na nuvem, mostrando como o AWS Step Functions permite criar soluções resilientes, escaláveis e de fácil manutenção, integradas com Lambda e S3.

