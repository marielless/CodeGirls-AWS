#  AWS Step Functions – Criação de Fluxos de Trabalho Visuais

##  Visão Geral
O **AWS Step Functions** é um serviço totalmente gerenciado da **Amazon Web Services (AWS)** que permite **criar, visualizar e executar fluxos de trabalho** para coordenar componentes distribuídos, como funções **AWS Lambda**, **ECS**, **S3**, **DynamoDB**, entre outros.

Ele usa **máquinas de estado (state machines)** para definir a lógica de execução dos processos, permitindo **automatizar e orquestrar** aplicações sem precisar gerenciar infraestrutura complexa.

---

##  Benefícios

- **Coordenação Visual:** Criação de fluxos de trabalho com uma interface intuitiva e fácil de usar.  
- **Integração com Serviços AWS:** Conecta-se com Lambda, S3, DynamoDB, SNS, SQS, ECS, entre outros.  
- **Gerenciamento de Estados:** Automatiza execução, controle de erros e repetição de etapas.  
- **Escalabilidade:** Lida com grandes volumes de eventos em paralelo.  
- **Observabilidade:** Acompanha execuções em tempo real e logs no CloudWatch.  
- **Custo-Efetivo:** Paga apenas pelas transições de estado realizadas.

---

##  Como Funciona

1. **Definição de Estados:** Cada estado representa uma etapa do fluxo de trabalho.  
2. **Máquina de Estados:** Define como as etapas se conectam e qual ação será executada.  
3. **Execução:** O Step Functions coordena os serviços seguindo a ordem e as condições definidas.

---

## Projeto de Exemplo – Processamento de Arquivos com S3 e Lambda

###  Objetivo
Criar um fluxo de trabalho que:
1. Detecta o upload de um arquivo no **S3**.  
2. Executa uma **função Lambda** para processar o arquivo.  
3. Armazena o resultado processado em outro bucket S3.

### Arquitetura
```
[S3 Bucket] -> [Step Function] -> [Lambda Function] -> [S3 Processed Bucket]
```


## Usando Workflows no Console da AWS

1. Acesse o serviço **Step Functions**.  
2. Clique em **Create state machine**.  
3. Escolha **Design your workflow visually**.  
4. Adicione os estados correspondentes (ex: Lambda Task, Choice State, Wait State).  
5. Salve e execute o fluxo.

---

## Usando o S3

- O **bucket de entrada** armazenará o arquivo original.  
- O **bucket de saída** conterá o arquivo processado após a execução da Lambda.  

O S3 pode ser configurado para acionar o Step Function automaticamente.


---

## Conclusão

O **AWS Step Functions** facilita a criação de **arquiteturas serverless escaláveis**, permitindo orquestrar vários serviços AWS de forma simples e visual.  
Com ele, é possível **automatizar fluxos complexos** de forma eficiente, reduzindo custos e aumentando a produtividade.

---

 **Autor:** Marielle Santos da Silva  
**Projeto Desafio DIO – AWS Step Functions**
