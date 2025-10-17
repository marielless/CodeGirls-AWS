# AWS CloudFormation

## O que é o CloudFormation

O **AWS CloudFormation** é um processo que auxilia na **automação de criação de recursos na AWS** por meio de **templates JSON ou YAML**.

Os templates podem ser reutilizados quantas vezes quiser, e você paga apenas pelas **stacks criadas** (conjunto de recursos, como EC2, RDS, S3, etc.).

Além de ser um processo automatizado, conseguimos **versionar** esses templates.  
É possível criar desde um **recurso simples**, como um EC2, até uma **arquitetura robusta** com vários recursos.

**Fluxo:**  
`template` → `CloudFormation` → `Stack`

---

## Template: Arquivo JSON com informações sobre os recursos

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

## Exemplo de Template JSON

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

