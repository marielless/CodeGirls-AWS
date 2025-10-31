# Amazon S3, AWS Lambda e LocalStack

## Amazon S3

O **Amazon S3** é um serviço de armazenamento em nuvem da AWS que permite armazenar e acessar dados de forma segura e escalável.  
Ele suporta qualquer tipo de arquivo (vídeo, áudio, imagens, documentos, etc) e é ideal para backup e armazenamento de objetos.

### Principais Vantagens do S3

- **Durabilidade:** altamente confiável, com redundância para proteger contra falhas.  
- **Disponibilidade:** garante acesso contínuo aos dados.  
- **Escalabilidade:** ajusta automaticamente a capacidade de armazenamento conforme a necessidade.  
- **Segurança:** oferece criptografia, controle de acesso e monitoramento de atividades.  

---

## AWS Lambda

O **AWS Lambda** é um serviço de computação serverless que permite executar código em resposta a eventos, sem a necessidade de gerenciar servidores.  
Basta fazer o upload do código e o Lambda se encarrega de executar automaticamente, escalando conforme a demanda.

### Principais Vantagens do Lambda

- **Execução sob demanda:** o código é executado apenas quando necessário, respondendo a eventos.  
- **Escalabilidade automática:** ajusta a capacidade automaticamente com base no número de eventos.  
- **Custo eficiente:** cobra apenas pelo tempo de execução e pela quantidade de solicitações.  
- **Integração com outros serviços AWS:** funciona como um conector entre diversos serviços da AWS, como S3, DynamoDB e API Gateway.  

---

## AWS Local com LocalStack

O principal objetivo do **LocalStack** é fornecer uma alternativa local para o desenvolvimento, teste e integração de serviços em nuvem, sem a necessidade de acessar a AWS real.  

Isso permite aos desenvolvedores economizar tempo e custos, especialmente em testes automatizados e em ambientes de integração contínua (CI/CD).  

### Serviços Suportados

Lambda, API Gateway, S3, DynamoDB, SNS, SQS, CloudFormation, entre outros.
