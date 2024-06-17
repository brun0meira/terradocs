# Estrutura do Projeto com Terraform

## Diretórios e Arquivos

Para organizar seu projeto Terraform, você precisará de alguns diretórios e arquivos básicos. Aqui está uma estrutura sugerida:

```
/meu-projeto-terraform
    ├── main.tf
    ├── variables.tf
    ├── outputs.tf
    └── .terraform/
```

### Descrição dos Arquivos

- **main.tf**: Este é o arquivo principal onde você define os recursos da infraestrutura. Neste tutorial, ele conterá a definição da instância EC2.
- **variables.tf** (opcional): Defina variáveis para parametrizar sua configuração. Isso ajuda a tornar seu código mais modular e reutilizável.
- **outputs.tf** (opcional): Defina saídas para obter informações sobre os recursos provisionados, como o endereço IP da instância EC2.
- **.terraform/**: Diretório criado automaticamente pelo Terraform para armazenar arquivos de estado e cache.

### Conteúdo do Arquivo main.tf

```hcl
provider "aws" {
  region = "us-east-1"
}

resource "aws_instance" "example" {
  ami           = "ami-0c02fb55956c7d316"  # Amazon Linux 2 AMI (HVM), SSD Volume Type
  instance_type = "t2.micro"

  tags = {
    Name = "TerraformExample"
  }
}
```

Neste arquivo, você especifica o provedor AWS e define um recurso de instância EC2 com a imagem AMI e o tipo de instância.

### Conteúdo do Arquivo variables.tf (Opcional)

```hcl
variable "region" {
  description = "The AWS region to deploy the instance."
  default     = "us-east-1"
}
```

Este arquivo define uma variável para a região AWS, permitindo que você altere a região sem modificar diretamente o arquivo main.tf.

### Conteúdo do Arquivo outputs.tf (Opcional)

```hcl
output "instance_id" {
  description = "The ID of the EC2 instance."
  value       = aws_instance.example.id
}

output "instance_public_ip" {
  description = "The public IP address of the EC2 instance."
  value       = aws_instance.example.public_ip
}
```

Este arquivo define saídas para o ID e o endereço IP público da instância EC2, facilitando a obtenção dessas informações após a criação da instância.