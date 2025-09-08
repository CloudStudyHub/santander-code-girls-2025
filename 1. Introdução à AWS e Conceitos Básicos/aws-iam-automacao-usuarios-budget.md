# Prática de AWS CLI – Criação e Automação de Usuários IAM

Hoje realizamos uma prática completa com **AWS CLI**, abordando segurança, automação e controle de custos na nuvem.  

## Passos Realizados

1. **Instalação e configuração do AWS CLI**  
   - Instalamos o AWS CLI no nosso ambiente de desenvolvimento.  
   - Configuramos credenciais de acesso e região padrão.    

2. **Criação de usuários e grupos IAM**  
   - Criamos um usuário IAM com **permissões administrativas**.  
   - Configuramos grupos de usuários para organizar e aplicar permissões de forma centralizada.  

3. **Automatização da criação de usuários**  
   - Utilizamos o script `scriptIAM.sh` junto com o arquivo CSV (`usuarios.csv`) para criar múltiplos usuários automaticamente.  
   - Configuramos perfis de login e exigimos redefinição de senha no primeiro acesso.
   
<img width="1407" height="1031" alt="cli-usuarios" src="https://github.com/user-attachments/assets/bb668011-98f4-4141-b9c9-605604740e2f" />
-
<img width="1388" height="755" alt="grupos-de-usuarios" src="https://github.com/user-attachments/assets/493667de-bc18-4495-a9e1-0a2aa9184cba" />

4. **Controle de custos e alertas de orçamento**  
   - Criamos um **orçamento na AWS** e configuramos alertas por e-mail para monitorar gastos.  
<img width="1323" height="682" alt="budget" src="https://github.com/user-attachments/assets/3e8dcf33-b370-4204-964b-722974dc88a8" />

Essa prática reforçou conceitos de **gerenciamento de identidade e acesso**, **automação de tarefas administrativas** e **controle financeiro** na AWS, mostrando como trabalhar de forma segura e eficiente na nuvem.
