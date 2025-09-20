# 📘 Documentação: Gerenciamento e Governança na AWS

Durante as aulas, seguimos a seguinte sequência de aprendizado e prática que acompanhei:

1. **Entendendo o que é o AWS CloudWatch**  
2. **Fundamentos do AWS CloudTrail para Auditoria e Segurança na AWS**
3. **Implementando sua Primeira Stack com AWS CloudFormation**
4. **Gerenciando Usuários e Permissões na AWS com Identity and Access Management (IAM)**  
5. **Entendendo e Gerenciando Policies e Roles na AWS**

---

## 1. AWS CloudWatch (Teórico)

Primeiro, aprendemos sobre o **CloudWatch**, de forma teórica, que permite **monitorar recursos e aplicações em tempo real**. Durante a explicação, vi como ele funciona para:

- **Métricas:** Monitorar CPU, memória, rede e outros recursos AWS.  
- **Logs:** Armazenar e organizar logs de aplicações e serviços para análise.  
- **Alarmes:** Criar alertas quando métricas atingem limites definidos.  
- **Dashboards:** Visualizar o estado da infraestrutura em painéis gráficos.  

> ⚠️ Como apaguei as práticas anteriores, **não tenho prints disponíveis** do CloudWatch. O aprendizado foi mais teórico.

---

## 2. AWS CloudTrail (Prática)

Depois, realizamos a prática do **CloudTrail**, registrando e auditando atividades na minha conta AWS.  
Os prints que tenho refletem **as ações que eu mesma executei** durante a prática.

### Principais funcionalidades que observei:

- **Auditoria completa:** Rastreia quem fez a ação, o que foi feito e quando aconteceu.  
- **Eventos críticos:** Permite verificar exclusões ou alterações importantes, como:

| Ação Visualizada  | Tipo de Recurso | Significado |
|------------------|----------------|------------|
| `DeleteBucket`   | AWS S3         | Exclusão de um bucket de armazenamento (perda de dados ou configuração). |
| `DeleteRolePolicy` | AWS IAM      | Remoção de uma política de permissão de uma Role (mudança no acesso). |
| `DeleteFunction` | AWS Lambda     | Exclusão de uma função de código serverless. |

**Prints:**  
- **Print 1:** Histórico de eventos geral
<img width="1920" height="1080" alt="Historico" src="https://github.com/user-attachments/assets/2eeb1257-9e04-4af7-acf9-c335939d409d" />

- **Print 2:** Detalhe da ação `DeleteBucket`
<img width="1920" height="1080" alt="DeleteBucket" src="https://github.com/user-attachments/assets/8cb6aad0-d074-4748-a31e-859f0f5526cc" />

- **Print 3:** Detalhe da ação `DeleteRolePolicy`
<img width="1920" height="1080" alt="DeleteRolePolicy" src="https://github.com/user-attachments/assets/99374413-1a47-4c46-986b-c1a1c5eeb302" />

- **Print 4:** Detalhe da ação `DeleteFunction`  
<img width="1920" height="1080" alt="DeleteFunction" src="https://github.com/user-attachments/assets/8ee0a026-e0a1-4b89-abe1-97eae821262b" />

### Detalhes rastreáveis por evento:

- **Executor:** `administrator`  
- **Origem:** `s3.amazonaws.com`  
- **IP de Origem:** `186.194.24.99`  

---

## 3. AWS CloudFormation (Prática)

Na sequência, realizamos o desafio de **CloudFormation**, que me permitiu **praticar a automação de infraestrutura** utilizando **templates YAML**.  

Durante a atividade, aprendi a:

- Criar **instâncias EC2** automatizadas.  
- Configurar **Security Groups** para acesso seguro (SSH e HTTP).  
- Implementar **scripts de inicialização** (`UserData`) para instalar servidores web automaticamente.  
- Aplicar **Infraestrutura como Código (IaC)**, garantindo que os recursos fossem reproduzíveis e versionáveis.  
- Validar e criar o **stack CloudFormation** no console AWS ou via CLI.

> ⚠️ Como parte do aprendizado, foquei na prática de criar recursos automatizados e observar o comportamento da infraestrutura provisionada, mesmo que não tenha mantido prints do CloudFormation.

### Repositório do Desafio
[Repositório do Desafio CloudFormation](https://github.com/CloudStudyHub/aws-cloudformation-primeira-stack)

---

## 4. Gerenciando Usuários e Permissões na AWS com Identity and Access Management (IAM) (Prática)

Nesta prática, revisamos e aplicamos os principais conceitos do **IAM (Identity and Access Management)**, focando em **automação via AWS CLI**, boas práticas de **governança** e **segurança de identidade** na nuvem.

### 🔁 Revisão de Conceitos:

- **Usuários IAM:** Identidades únicas com credenciais para acesso à AWS.  
- **Grupos IAM:** Agrupamento lógico de usuários que compartilham permissões.  
- **Policies (Políticas):** Regras que definem permissões específicas (em JSON).  
- **Roles:** Permissões temporárias atribuídas a serviços, usuários ou contas confiáveis.

---

### ⚙️ Ações Práticas com AWS CLI

Utilizei o **AWS CLI** para criar e configurar usuários de forma automatizada, associando-os a grupos com permissões predefinidas:

#### 👥 Usuários Criados:

- `ze.gota`  
- `voila.semcorda`  
- `gringo.brasileiro`  
- *(e outros fictícios)*

#### 🧩 Grupos IAM Criados e Utilizados:

- `GPO-AWS-Infraestrutura`  
- `GPO-AWS-Negocios`

Esses grupos foram configurados para carregar **políticas específicas** de acesso conforme o papel de cada usuário na organização fictícia.

---

### 🚨 Observações Importantes

#### 🔒 Segurança e Políticas de Senha:

Durante a criação de usuários, o CLI retornou o seguinte erro:

```bash
An error occurred (PasswordPolicyViolation) when calling the CreateLoginProfile operation: Password should have a minimum length of 8 
```
Esse erro reforça a importância da aplicação de políticas de senha rígidas na conta AWS, garantindo governança e segurança básica de identidades.

### 🤖 Automação com CLI:

Todos os usuários foram adicionados aos grupos corretos via script CLI.

Isso garante que herdem automaticamente as Policies adequadas para suas funções (infraestrutura ou negócios).

Reduz erros manuais e facilita a governança em larga escala.

**Prints:**  
- **Print 1: Execução dos comandos no AWS CLI para criação de usuários e associação a grupos**
<img width="1920" height="1080" alt="CLI" src="https://github.com/user-attachments/assets/a5bcfceb-4515-4c20-9a87-548381139069" />

- **Print 2: Visualização no AWS Console**
<img width="1920" height="1080" alt="Console" src="https://github.com/user-attachments/assets/32c1555b-b6f3-4973-932f-8aab38f8762e" />

---
## 5. Entendendo e Gerenciando Policies e Roles na AWS (Teórico)

Nesta etapa do aprendizado, explorei os **conceitos fundamentais de Policies e Roles** no IAM por meio do **AWS Console**, sem execução prática com CLI.

### 📚 O que aprendi:

- **Policies (Políticas):** São documentos em formato JSON que definem permissões específicas (como `s3:ListBucket`, `ec2:StartInstances`, etc.).  
  - Podem ser **gerenciadas pela AWS** (AWS Managed Policies) ou **customizadas pelo usuário** (Customer Managed Policies).  
  - São **atribuídas a usuários, grupos ou roles**.

- **Roles (Funções IAM):**  
  - Permitem a **atribuição temporária de permissões** a usuários, serviços ou contas externas.
  - São **reutilizáveis** por diferentes entidades autorizadas por sua **trust policy** (exemplo: EC2 assumindo uma Role com acesso ao S3).
  - Utilizadas frequentemente por **serviços AWS**, como Lambda, EC2, ECS, etc.

### 👀 Atividades realizadas:

- Naveguei no **IAM Console** para visualizar:
  - Políticas atribuídas a grupos e usuários.
  - Criação e estrutura de políticas em JSON.
  - Trust policy de roles.
  - Diferença entre políticas gerenciadas e inline.

> ⚠️ Esta atividade foi **teórica e de exploração via Console**, sem execução de comandos.

---

## ✅ Conclusão

- Com o **CloudWatch**, aprendi a importância do monitoramento contínuo da infraestrutura, mesmo que de forma teórica.  
- Com o **CloudTrail**, pude colocar em prática a auditoria e rastreabilidade das ações que executei na conta AWS.  
- Com o **CloudFormation**, automatizei a criação de infraestrutura com templates YAML.  
- Com o **IAM (via CLI)**, criei usuários, grupos e associei permissões com foco em governança.  
- Com a análise de **Policies e Roles**, entendi como estruturar controle de acesso granular e reutilizável na AWS.

Essas ferramentas e conceitos me deram **uma visão completa de gerenciamento, auditoria e governança na AWS**, consolidando conhecimentos essenciais para ambientes em nuvem empresariais.
