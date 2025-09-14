# Documentação de Práticas - Armazenamento e CDN na AWS

Este documento reúne as práticas realizadas com os serviços **Amazon S3**, **Amazon Glacier** e **Amazon CloudFront**, mostrando passo a passo desde a configuração até a validação do funcionamento.

---

## 📂 Amazon S3 - Simple Storage Service

### 1. Criação do Bucket
- Nome do bucket: `codegirls-dio`
- Região: `us-east-1 (Norte da Virgínia)`
- Configurações com bloqueio de acesso público desativado.

### 2. Liberação de Acesso Público
- Ajuste das configurações de **Bloqueio de Acesso Público** (desativando restrições).
- Criação de **Bucket Policy** permitindo acesso público de leitura aos objetos.
  
📸 *Prints:*  
<img width="1919" height="907" alt="bucket" src="https://github.com/user-attachments/assets/83c788ff-dfb8-4574-99a1-5a02247ee88d" />
---

### 3. Upload de Arquivo
- Arquivo enviado: `Documento A4 Planner Semanal`
- Tipo: `image/png`
- Status: Upload bem-sucedido ✅

📸 *Prints:*  
<img width="1920" height="905" alt="arquivo" src="https://github.com/user-attachments/assets/32df56f4-a724-410a-ae7f-40c6468fd615" />
<img width="1920" height="1034" alt="visualização" src="https://github.com/user-attachments/assets/cfd28e5b-a626-472d-b488-5a89380fb7ea" />
---

### 4. Uso do AWS Policy Generator
- Política gerada via **AWS Policy Generator** para permitir `s3:GetObject`.

📸 *Prints:*  
<img width="1920" height="997" alt="policygen" src="https://github.com/user-attachments/assets/930782b0-b654-48fd-9db6-75c919542c57" />
---
### Conceito
- O Amazon S3 (Simple Storage Service) é um serviço de **armazenamento de objetos** que oferece alta durabilidade, escalabilidade e segurança.  
- Ele é usado para guardar qualquer tipo de dado (imagens, vídeos, documentos, backups, logs, etc.) e pode ser acessado de forma pública ou privada.  
- Além disso, permite controlar permissões com **Bucket Policies**, **ACLs** e integração com outros serviços da AWS.
---
## 🧊 Amazon S3 Glacier

### Observação Importante
A prática completa com o **Amazon S3 Glacier** **não pôde ser realizada**, pois o serviço **não está incluso no Free Tier da AWS**.  
Por esse motivo, não foi possível criar efetivamente um **Vault** ou enviar arquivos para arquivamento.

### O que foi feito
- Acesso à tela de criação de Vault no S3 Glacier.  
- Visualização da interface e opções de configuração.  
- Exploração da tela do **AWS Snow**, que também aparece como serviço de transferência de dados.

📸 *Prints:*
<img width="1920" height="1080" alt="s3glacier" src="https://github.com/user-attachments/assets/b7f70349-40d5-44e3-82f5-7693361490f9" />
<img width="1920" height="1080" alt="snowball" src="https://github.com/user-attachments/assets/504cfb5f-a246-43fa-ab16-e2bdab9299f7" />

### Conceito
- O Amazon S3 Glacier é usado para **armazenamento de longo prazo** com custo reduzido.  
- Já o **AWS Snow** é uma família de dispositivos físicos que permitem **migração e transporte seguro de grandes volumes de dados** para a nuvem.
---

## 🌍 Amazon CloudFront

A prática completa com o **Amazon CloudFront** **não pôde ser realizada**, pois não chegamos a criar a distribuição.  

### O que foi feito
- Acesso à tela de criação de distribuição no console da AWS.  
- Visualização das opções de configuração, incluindo:
  - Origem (S3 ou outro endpoint).  
  - Definição de cache behavior.  
  - Configuração de segurança (HTTPS).  
  - Seleção de regiões e preço.  

📸 *Prints:*  
<img width="1920" height="1080" alt="cloudfront" src="https://github.com/user-attachments/assets/a3bf3fd3-c494-4eee-a1d4-752fd583594a" />


### Conceito
- O Amazon CloudFront é uma **rede de entrega de conteúdo (CDN)** que distribui dados, vídeos, aplicações e APIs globalmente com baixa latência e alta transferência.  
- Ele funciona integrado ao **Amazon S3** para entregar arquivos de forma mais rápida e eficiente para usuários no mundo todo.
---

## ✅ Conclusão
Com estas práticas, foi possível:

- ✅ Configurar um bucket no **Amazon S3**.  
- ✅ Realizar upload e liberar acesso público a arquivos.  
- ✅ Gerar políticas com o **AWS Policy Generator**.  
- 👀 Explorar a tela de criação do **Amazon S3 Glacier** e entender seu uso para arquivamento de longo prazo (não realizado por não estar no Free Tier).  
- 👀 Visualizar a tela de criação do **Amazon CloudFront** e compreender como funciona a entrega de conteúdo globalmente (distribuição não criada).  

📌 Assim, foi possível ter uma visão prática dos recursos de **armazenamento e distribuição de conteúdo** na AWS, entendendo como cada serviço se complementa:
- O **S3** para armazenamento de objetos.  
- O **Glacier** para arquivamento de longo prazo.  
- O **CloudFront** para distribuição com baixa latência no mundo todo. 

