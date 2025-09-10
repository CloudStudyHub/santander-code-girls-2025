# 🚀 Criando sua Primeira Instância Amazon EC2  

Este documento registra a prática realizada no curso **Criando sua Primeira Instância Amazon EC2**, incluindo a criação e conexão de instâncias Linux e Windows, configuração de pares de chaves e grupos de segurança.  

---

## ✅ O que foi feito  
- Criação de uma instância **Linux (Amazon Linux 2)**.  
- Criação de uma instância **Windows Server 2019**.  
- Geração de **Key Pairs** para autenticação segura.  
- Configuração de **Security Groups** para permitir conexões (SSH e RDP).  
- Conexão à instância **Linux via MobaXterm**.  
- Conexão à instância **Windows via Remote Desktop (RDP)**.  

---

## ⚙️ Configurações  

### 🔹 Instância Linux  
- **Nome:** servidor01  
- **AMI:** Amazon Linux 2 (Free Tier)  
- **Tipo de instância:** t3.micro  
- **Par de chaves:** ChavesLinux.pem  
- **Grupo de segurança:**  
  - Porta 22 liberada para SSH (acesso pelo meu IP) 

### 🔹 2 Instância Linux  
- **Nome:** servidor02  
- **AMI:** Amazon Linux 2 (Free Tier)  
- **Tipo de instância:** t3.micro  
- **Par de chaves:** ChavesLinux.pem  
- **Grupo de segurança:**  
  - Porta 22 liberada para SSH (acesso pelo meu IP)   

### 🔹 Instância Windows  
- **Nome:** EC2-Windows  
- **AMI:** Microsoft Windows Server 2025 Base  
- **Tipo de instância:** t3.micro  
- **Par de chaves:** ChavesWindows.pem  
- **Grupo de segurança:**  
  - Porta 3389 liberada para RDP (acesso pelo meu IP)  

---

## 🔑 Segurança  
- **Key Pairs**: utilizados para autenticação sem senha.  
- **Security Groups**: configurados para liberar apenas as portas necessárias (22 e 3389).  
- Acesso restrito ao **meu endereço IP** para maior proteção.  

---

## 🛠️ Ferramentas utilizadas  
- **Amazon EC2 (AWS)**  
- **MobaXterm** → conexão via SSH (Linux)  
- **Remote Desktop (RDP)** → conexão via Windows  

---

## 📚 Aprendizados  
- Como criar e configurar instâncias Linux e Windows na AWS.  
- Diferença entre acessos via **SSH** e **RDP**.  
- Importância da utilização de **pares de chaves** para segurança.  
- Criação de **Security Groups** controlando portas específicas.  

---
## 🔹 Instâncias
Instâncias criadas no console:  
<img width="1920" height="1080" alt="Instancias" src="https://github.com/user-attachments/assets/fa345589-54bc-4860-abc6-3fad761ad0dd" />

---

## 🔹 Conexão Linux via MobaXterm
Print da sessão conectada:  
<img width="1920" height="1080" alt="Conectar com MobaXterm" src="https://github.com/user-attachments/assets/3f294f0a-1e43-4f7d-8c80-9ed261ae5894" />

---

## 🔹 Conexão Windows via RDP
Print da conexão com Remote Desktop: 
<img width="1426" height="887" alt="Conectar RDS" src="https://github.com/user-attachments/assets/1d931e1f-062c-4dec-b285-c5ea8226014d" />
