# Outputs

## Evidências do Passo a Passo

### 1. Verificando a Instalação do Terraform

Após instalar o Terraform, você pode verificar a instalação executando o comando `terraform -v`. 

**Comando:**
```sh
terraform -v
```

**Descrição do Print:**
Este print mostra a versão do Terraform instalada no seu sistema, confirmando que a instalação foi bem-sucedida.

![Verificação do Terraform](https://i.ibb.co/b7THZqL/terraform-version.png)

---

### 2. Verificando a Instalação do AWS CLI

Depois de instalar o AWS CLI, você pode verificar a instalação executando o comando `aws --version`.

**Comando:**
```sh
aws --version
```

**Descrição do Print:**
Este print mostra a versão do AWS CLI instalada, garantindo que a instalação foi concluída corretamente.

![Verificação do AWS CLI](https://i.ibb.co/ZHq4JXT/aws-version.png)

---

### 3. Criando o Arquivo main.tf

Crie um arquivo de configuração Terraform chamado `main.tf` com o seguinte conteúdo:

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

**Descrição do Print:**
Este print mostra o conteúdo do arquivo `main.tf` criado no seu editor de texto.

![Arquivo main.tf](https://i.ibb.co/bvfVtfF/main-archive.png)

---

### 4. Inicializando o Terraform

Inicialize o Terraform executando o comando `terraform init` no diretório onde está o arquivo `main.tf`.

**Comando:**
```sh
terraform init
```

**Descrição do Print:**
Este print mostra a saída do comando `terraform init`, indicando que o Terraform foi inicializado com sucesso.

![Inicialização do Terraform](https://i.ibb.co/b3hjBfm/terraform-init.png)

---

### 5. Planejando a Infraestrutura

Execute o comando `terraform plan` para ver o que será criado.

**Comando:**
```sh
terraform plan
```

**Descrição do Print:**
Este print mostra a saída do comando `terraform plan`, detalhando os recursos que serão criados.

![Planejamento da Infraestrutura](https://i.ibb.co/RP8Ys4v/terraform-plan.png)

---

### 6. Aplicando a Configuração

Para criar a instância EC2, execute o comando `terraform apply` e digite `yes` quando solicitado.

**Comando:**
```sh
terraform apply
```

**Descrição do Print:**
Este print mostra a saída do comando `terraform apply`, indicando a criação bem-sucedida da instância EC2.

![Aplicação da Configuração](https://i.ibb.co/ZM2DSRm/terraform-apply.png)

---

### 7. Verificando a Instância na AWS

Para verificar se a instância foi criada, acesse o AWS Management Console, navegue até o serviço EC2 e confira a lista de instâncias.

**Descrição do Print:**
Este print mostra a instância EC2 criada na AWS. Ele inclui detalhes como o ID da instância, tipo de instância, estado e nome ("TerraformExample").

![Verificando EC2](https://i.ibb.co/dBJ7GYd/verify-ec2.png)

---

### 8. Limpando a Infraestrutura

Para destruir a instância criada, execute o comando `terraform destroy` e digite `yes` quando solicitado.

**Comando:**
```sh
terraform destroy
```

**Descrição do Print:**
Este print mostra a saída do comando `terraform destroy`, indicando a destruição bem-sucedida da instância EC2.

![Destruição da Infraestrutura](https://i.ibb.co/fx2ZGs7/terraform-destroy.png)