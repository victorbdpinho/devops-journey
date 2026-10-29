# Installation Docker em Ubuntu

## 1. Atualizacao e Manutencao do Sistema Ubuntu

### Atualiza a lista de pacotes disponíveis nos repositórios oficiais da internet
sudo apt update

### Efetivamente descarrega e instala as atualizações de todos os programas e pacotes do sistema que tenham versões mais recentes disponíveis
sudo apt-get upgrade -y


## 2. Instalacao Automatica do Docker Engine

### Execucao do script oficial fornecido pela Docker para descarregar e instalar o daemon do Docker Engine de forma automatizada no Linux.
### Descarregar o script oficial de instalacao automatica da Docker
curl -fsSL https://get.docker.com -o get-docker.sh

### Executar o script descarregado com privilegios de administrador (root)
sudo sh get-docker.sh


## 3. Configuracao de Permissoes (Executar sem sudo)

### Por predefinição, o daemon do Docker exige privilegios de root. Esta etapa atribui permissoes ao utilizador atual para gerir contentores sem necessitar de anteceder cada comando com sudo.
### Adicionar o utilizador atual ($USER) ao grupo do sistema reservado ao Docker
sudo usermod -aG docker $USER

### Recarregar as permissoes de grupo do utilizador na sessao atual do terminal sem necessidade de reiniciar o sistema
newgrp docker


## 4. Validacao da Instalacao do Docker

### Execucao de um teste pratico utilizando a imagem oficial "hello-world" para confirmar que o servico do Docker esta ativo e operacional.
### Descarregar e executar o contentor de teste oficial para validar o funcionamento do Docker
docker run hello-world


## 5. Comandos de Verificacao e Gestao de Contentores

### Comandos de inspecao utilizados para monitorizar, listar e verificar o estado dos contentores no ambiente local.
### Listar apenas os contentores que estao atualmente em execucao ativa no sistema
docker ps

### Listar todos os contentores do sistema, incluindo os que estao ativos e os que ja pararam ou finalizaram
docker ps -a

### Listar apenas os identificadores numéricos (IDs) dos contentores em execucao ativa
docker ps -q

---

# Installation AWS-CLI

## Baixar o pacote de instalacao do AWS CLI em formato zip a partir do site oficial da Amazon
curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"

## Descompactar o ficheiro zip descarregado no diretorio atual
unzip awscliv2.zip

## Executar o script de instalacao do AWS CLI com privilegios de administrador
sudo ./aws/install

## Verificar instalacao com a versao atual da ferramenta
aws --version

---

# Installation Azure CLI

## Descarregar e executar o script oficial de instalacao da Azure CLI no Ubuntu
curl -sL https://aka.ms/InstallAzureCLIDeb | sudo bash

## Verificar instalacao com a versao atual da ferramenta
az version

---

# Installation Terraform

## Adicionar a chave GPG oficial da HashiCorp para validar a seguranca do repositorio
curl -fsSL https://apt.releases.hashicorp.com/gpg | sudo gpg --dearmor -o /usr/share/keyrings/hashicorp-archive-keyring.gpg

## Adicionar o repositorio oficial do Terraform a lista de fontes do apt no sistema
echo "deb [signed-by=/usr/share/keyrings/hashicorp-archive-keyring.gpg] https://apt.releases.hashicorp.com $(lsb_release -cs) main" | sudo tee /etc/apt/sources.list.d/hashicorp.list

## Atualizar os repositorios do sistema e instalar o Terraform
sudo apt update && sudo apt install terraform -y

## Verificar instalacao com a versao atual da ferramenta
terraform --version

---

# Installation Ansible

## Atualizar indices e instalar o Ansible de forma automatizada no Ubuntu
sudo apt install ansible -y
