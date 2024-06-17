# Setup e Passo a Passo para Criar uma Instância EC2 com Terraform

## Pré-requisitos

Antes de começar, certifique-se de que você tem uma conta na [AWS Academy](https://awsacademy.instructure.com/).

## Setup Linux

### Instalando o Terraform CLI

1. Abra o terminal.
2. Adicionar a chave GPG do repositório do HashiCorp:
```bash
wget -O- https://apt.releases.hashicorp.com/gpg | sudo gpg --dearmor -o /usr/share/keyrings/hashicorp-archive-keyring.gpg
```
3. Adicionar o repositório do HashiCorp à lista de fontes APT:
```bash
echo "deb [signed-by=/usr/share/keyrings/hashicorp-archive-keyring.gpg] https://apt.releases.hashicorp.com $(lsb_release -cs) main" | sudo tee /etc/apt/sources.list.d/hashicorp.list
```
4. Atualizar a lista de pacotes e instalar o Terraform:
```bash
sudo apt update && sudo apt install terraform
```

### Instalando o AWS CLI

1. Abra o terminal.
2. Baixe o instalador do AWS CLI:
```bash
curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
```
3. Extraia o arquivo ZIP:
```bash
unzip awscliv2.zip
```
4. Instale o AWS CLI:
```bash
sudo ./aws/install
```
5. Verifique a instalação executando:
```bash
aws --version
```

### Configurando as Credenciais da AWS

1. Configure suas credenciais da AWS executando o comando:
   ```bash
   aws configure
   ```
2. Forneça suas credenciais de acesso (AWS Access Key ID, AWS Secret Access Key, região padrão e formato de saída).
3. Abra o terminal e navegue até o diretório de configuração da AWS para configurar o AWS Access Token diretamente no arquivo de credenciais:
```bash
    cd ~/.aws/
```
a) Abra o arquivo `credentials` em um editor de texto:
```bash
nano credentials
```
b) Adicione ou edite a seção com o seguinte conteúdo:
```plaintext
[default]
aws_access_key_id = YOUR_ACCESS_KEY_ID
aws_secret_access_key = YOUR_SECRET_ACCESS_KEY
aws_session_token = YOUR_SESSION_TOKEN
```

## Setup Windows

### Instalando o Terraform CLI

1. Abra o PowerShell como Administrador.
2. Baixe o Terraform executando o comando:
```powershell
Invoke-WebRequest -Uri https://releases.hashicorp.com/terraform/1.0.11/terraform_1.0.11_windows_amd64.zip -OutFile terraform.zip
```
3. Extraia o arquivo ZIP:
```powershell
Expand-Archive -Path terraform.zip -DestinationPath C:\terraform
```
4. Adicione o Terraform ao PATH do sistema:
```powershell
[System.Environment]::SetEnvironmentVariable('PATH', $env:PATH + ';C:\terraform', [System.EnvironmentVariableTarget]::Machine)
```
5. Verifique a instalação executando:
```powershell
terraform -v
```

### Instalando o AWS CLI

1. Abra o PowerShell como Administrador.
2. Baixe o instalador do AWS CLI executando:
```powershell
Invoke-WebRequest -Uri https://awscli.amazonaws.com/AWSCLIV2.msi -OutFile AWSCLIV2.msi
```
3. Instale o AWS CLI executando:
```powershell
Start-Process msiexec.exe -Wait -ArgumentList '/I AWSCLIV2.msi /quiet'
```
4. Verifique a instalação executando:
```powershell
aws --version
```

### Configurando as Credenciais da AWS

1. Configure suas credenciais da AWS executando o comando:
```powershell
aws configure
```
2. Forneça suas credenciais de acesso (AWS Access Key ID, AWS Secret Access Key, região padrão e formato de saída). 
3. Abra o PowerShell e navegue até o diretório de configuração da AWS para configurar o AWS Access Token diretamente no arquivo de credenciais:
```powershell
cd ~\.aws\
```
a) Abra o arquivo `credentials` em um editor de texto:
```powershell
notepad credentials
```
b) Adicione ou edite a seção com o seguinte conteúdo:
```plaintext
[default]
aws_access_key_id = YOUR_ACCESS_KEY_ID
aws_secret_access_key = YOUR_SECRET_ACCESS_KEY
aws_session_token = YOUR_SESSION_TOKEN
```