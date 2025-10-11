# AMIs e Snapshots no Amazon EC2

## Amazon Machine Image (AMI)
Uma **AMI (Amazon Machine Image)** é uma imagem pré-configurada que contém as informações necessárias para iniciar uma instância no **Amazon EC2**, incluindo:
- Sistema operacional
- Servidor de aplicações
- Aplicações e configurações adicionais

### Principais pontos sobre AMIs
1. **Criação** → Podem ser criadas a partir de instâncias em execução ou paradas.  
   _(Permite capturar um instantâneo do ambiente configurado)._

2. **AMIs públicas e privadas** →  
   - **Públicas**: fornecidas pela AWS e pela comunidade.  
   - **Privadas**: criadas pelo usuário para maior segurança e personalização.  

3. **Personalização** → Configure uma instância e crie uma AMI personalizada para replicar o mesmo ambiente.  

4. **Inicialização de instâncias** → A AMI fornece as informações necessárias para iniciar uma instância (volume raiz, permissões etc.).  

5. **Tipos de AMI** → Amazon Linux, Windows e outras distribuições, escolhidas conforme os requisitos da aplicação.  


---

## Snapshots com Amazon EBS
O **Amazon Elastic Block Store (EBS)** fornece **armazenamento em bloco confiável** para instâncias do EC2.

- **EBS Snapshots** são **backups em pontos no tempo** dos volumes do EBS, armazenados no **Amazon S3**.  
- **Recuperação de desastres (DR):** snapshots podem ser copiados para outras regiões.  
- **Otimização:** possível configurar volumes SSD para cargas com alto uso de I/O.  

### Benefícios dos Snapshots
- Criação de novos volumes a partir de snapshots existentes  
- Aumento da durabilidade dos dados  
- Mecanismo de **backup e restauração** para volumes EBS
 

---

## ✅ Conclusão
- **AMIs** permitem criar, personalizar e inicializar instâncias de forma rápida e consistente.  
- **Snapshots do EBS** oferecem um meio seguro e durável de backup, recuperação e replicação de volumes.  

Ambos os recursos são fundamentais para garantir **escalabilidade, resiliência e continuidade** em soluções na nuvem com **AWS**.
