# Documentação de Aprendizado: Serviços Intermediários e Avançados AWS

Este documento resume os principais aprendizados sobre serviços intermediários e avançados da AWS, incluindo **AWS Lambda**, **Amazon ECS/EKS** e **Amazon SNS/SQS**. Ele aborda conceitos, práticas realizadas e ferramentas utilizadas.

---

🚀 **O que foi feito**

### 1. AWS Lambda

**Descrição:** Criação de uma função serverless utilizando Python 3.11 para se integrar à API pública do ViaCEP.

**Detalhes da Implementação:**

* A função **FunctionCodeGirls** foi criada em Python 3.11.
* Foi adicionada a camada (Lambda Layer) **Klayers-p311-requests** para permitir o uso da biblioteca `requests`.
* O código faz uma requisição para a URL `https://viacep.com.br/ws/01001000/json/` e extrai o campo `ibge` da resposta JSON.

**Código da Função:**

```python
import json
import requests

def lambda_handler(event, context):
    url = 'https://viacep.com.br/ws/01001000/json/'
    resultado = requests.get(url, verify=False)
    numeros = json.loads(resultado.text)['ibge']

    return {
        'statusCode': 200,
        'body': json.dumps(numeros)
    }
```
🛠️ **Configurações Adicionais e Monitoramento**

**Visualização de Logs no CloudWatch**

* O **AWS Lambda** se integra automaticamente com o CloudWatch para registrar logs de execução, essencial para monitorar a função e solucionar erros.
* Passos:

  1. Acesse a função Lambda no console.
  2. Clique na aba **Monitorar**.
  3. Clique em **Visualizar logs no CloudWatch**.
  4. O CloudWatch será aberto mostrando os grupos de logs da função, incluindo cada execução, tempo de duração e mensagens de `print()` ou erros.

**Adicionar um Gatilho (Trigger) S3**

* Permite que a função Lambda seja executada automaticamente quando um objeto é carregado em um bucket.
* Passos:

  1. Acesse a função Lambda no console.
  2. No diagrama da função, clique em **+ Adicionar gatilho**.
  3. Selecione **S3** como serviço.
  4. Escolha o bucket desejado.
  5. Em **Tipo de evento**, selecione, por exemplo, **All object create events**.
  6. Marque a caixa de confirmação para conceder permissão ao S3.
  7. Clique em **Adicionar**.

---

📸 **Prints**

* Visão geral da função Lambda com as propriedades de código e camadas.
<img width="1916" height="936" alt="lambda" src="https://github.com/user-attachments/assets/81f4614e-b429-4116-9921-77830d22eb89" />

<img width="1920" height="1080" alt="camadas" src="https://github.com/user-attachments/assets/3974ad48-9a52-4bf1-b95c-ce78ae0e5756" />

* Exemplo de ARNs do projeto Klayers no GitHub..
<img width="1920" height="1080" alt="repositorio" src="https://github.com/user-attachments/assets/43ccd139-a312-4bea-88fd-367f58721f9f" />
<img width="1913" height="986" alt="arn" src="https://github.com/user-attachments/assets/dd343c97-9019-4cf9-ae4a-c9548d9ee69b" />

* Resultado da execução da função, mostrando a saída JSON com o código IBGE.
<img width="1920" height="1024" alt="saidajson" src="https://github.com/user-attachments/assets/1cda86ca-b1fd-4655-a2b0-b32d7ee52cdb" />

* Logs Amazon CloudWatch
 <img width="1920" height="1080" alt="cloudwatch" src="https://github.com/user-attachments/assets/2f6f526a-2243-44cd-beba-d05f209ece2d" />

---

### 2. Amazon ECS e EKS

**Descrição:** Estudo sobre os serviços de orquestração de containers da AWS, focando em suas finalidades, diferenças e quando utilizar cada um.

### Conceitos-Chave Estudados

- **Container:** Unidade de software que empacota código e dependências para garantir consistência entre ambientes (ex: Docker).  
- **Orquestração:** Automação do deploy, gerenciamento e escalabilidade de containers.  

### Análise Comparativa: ECS vs. EKS

| Característica | Amazon ECS (Elastic Container Service) | Amazon EKS (Elastic Kubernetes Service) |
|----------------|-----------------------------------------|------------------------------------------|
| **Definição**  | Serviço de orquestração nativo e gerenciado pela AWS. | Serviço gerenciado que executa Kubernetes (padrão de mercado) na AWS. |
| **Complexidade** | Mais simples. Curva de aprendizado menor e integração profunda com o ecossistema AWS. | Mais complexo. Exige conhecimento do ecossistema Kubernetes, mas oferece maior flexibilidade e portabilidade. |
| **Quando Usar** | Ideal para equipes que buscam uma solução simples, rápida e totalmente integrada ao ambiente AWS. | Ideal para equipes que já utilizam Kubernetes, precisam de funcionalidades avançadas ou planejam uma estratégia multicloud. |

---

## 3. Amazon SNS e SQS 

**Descrição:** Análise dos serviços de mensageria da AWS para a criação de arquiteturas de software desacopladas, escaláveis e resilientes.

### Conceitos-Chave Estudados

- **Amazon SQS (Simple Queue Service):** Serviço de fila que permite que componentes se comuniquem de forma assíncrona.  
  Um componente (produtor) envia mensagens, e outro (consumidor) as processa em seu próprio ritmo.  
  Garante a entrega e o processamento de tarefas.  

- **Amazon SNS (Simple Notification Service):** Serviço de publicação/assinatura (Pub/Sub).  
  Uma mensagem é enviada a um tópico, e o SNS a distribui para múltiplos assinantes (filas SQS, funções Lambda, e-mails, etc.).  

### Padrões de Fila no Amazon SQS

- **Standard Queue (Padrão):**  
  - Alta taxa de transferência.  
  - Garante entrega de mensagens **pelo menos uma vez**.  
  - A ordem das mensagens **não é garantida**.  
  - Indicado para sistemas que priorizam escalabilidade e toleram pequenas variações de ordem.  

- **FIFO Queue (First-In, First-Out):**  
  - Garante que as mensagens sejam entregues **exatamente uma vez** e **na ordem exata** em que foram enviadas.  
  - Limitada em throughput em relação à fila padrão.  
  - Ideal para cenários em que a **ordem e unicidade** das mensagens são críticas (ex: transações financeiras, pedidos de e-commerce).  

---

