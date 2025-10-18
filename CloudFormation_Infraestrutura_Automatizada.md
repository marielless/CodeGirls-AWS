# AWS CloudFormation: Infraestrutura Automatizada

O **AWS CloudFormation** é um processo que auxilia na **automação de criação de recursos na AWS** por meio de **templates JSON ou YAML**.

Os templates podem ser reutilizados quantas vezes quiser, e você paga apenas pelas **stacks criadas** (conjunto de recursos, como EC2, RDS, S3, etc.).

Além de ser um processo automatizado, conseguimos **versionar** esses templates.  
É possível criar desde um **recurso simples**, como um EC2, até uma **arquitetura robusta** com vários recursos.

**Fluxo:**  
`template` → `CloudFormation` → `Stack`

---

## Processo do CloudFormation

1. **Template**  
   Crie ou utilize um template existente (em JSON ou YAML) que descreve os recursos desejados.

2. **Armazenamento**  
   Salve o template localmente ou em um **bucket S3**.

3. **Stack (Pilha)**  
   Use o **AWS CloudFormation** para criar uma stack com base no template.  
   O CloudFormation constrói e configura automaticamente os recursos definidos.

---

## JSON no CloudFormation

O **JSON** é o formato tradicional e originalmente suportado pelo **AWS CloudFormation**, com uma estrutura baseada em **pares chave-valor**.

### Exemplo de Template JSON

```json
{
  "Resources": {
    "MyInstance": {
      "Type": "AWS::EC2::Instance",
      "Properties": {
        "InstanceType": "t2.micro",
        "ImageId": "ami-12345678"
      }
    }
  }
}
```

---

## YAML no CloudFormation

O **YAML** é o formato preferido por muitos devido à sua **simplicidade**.  
A seguir, um exemplo **equivalente ao JSON anterior**.

### Exemplo de Template YAML

```yaml
Resources:
  MyInstance:
    Type: "AWS::EC2::Instance"
    Properties:
      InstanceType: "t2.micro"
      ImageId: "ami-12345678"
```

---

## Template: Arquivo JSON com informações sobre nossos recursos

### AWS::S3::Bucket
Aqui definimos 2 buckets para registros e backups.

### DeletionPolicy
Aqui temos uma política que retém os dados dos S3 buckets.

### AccessControl
Definimos o modo de acesso — neste caso é `Private`.

### LifecycleConfiguration
Permite criar uma política de ciclo de vida.  
Neste caso, removerão os arquivos com mais de **15** ou **30 dias**.

---

## Exemplo de Template JSON com Buckets

```json
"S3BackupBucket": {
  "Type": "AWS::S3::Bucket",
  "DeletionPolicy": "Retain",
  "Properties": {
    "AccessControl": "Private",
    "BucketName": "opentodo-backups",
    "LifecycleConfiguration": {
      "Rules": [
        {
          "ExpirationInDays": 15,
          "Status": "Enabled"
        }
      ]
    }
  }
},
"S3LogBucket": {
  "Type": "AWS::S3::Bucket",
  "DeletionPolicy": "Retain",
  "Properties": {
    "AccessControl": "Private",
    "BucketName": "opentodo-logs",
    "LifecycleConfiguration": {
      "Rules": [
        {
          "ExpirationInDays": 30,
          "Status": "Enabled"
        }
      ]
    }
  }
}
```

---

### Imagem ilustrativa
*(Adicione aqui a imagem representando o fluxo Template → CloudFormation → Stack)*
