# Introdução ao Terraform
> Daniel Vieira, Professor de DevOps da Ada

## Introdução ao Terraform
Terraform é uma ferramenta de infraestrutura como código (IaC) que permite criar, alterar e versionar infraestrutura de forma segura e eficiente. O Terraform é uma ferramenta de código aberto desenvolvida pela HashiCorp e é uma das ferramentas mais populares para gerenciar infraestrutura como código. A partir de uma configuração declarativa, o Terraform permite criar e gerenciar recursos de infraestrutura em diversos provedores de nuvem, como AWS, Azure, Google Cloud, entre outros.

> > [!TIP]
> [What is Terraform?](https://developer.hashicorp.com/terraform/intro) Terraform is an infrastructure as code tool that lets you build, change, and version cloud and on-prem resources safely and efficiently.


## Workflow e lifecycle do Terraform
O Terraform segue um workflow de execução que envolve a criação, alteração e remoção de recursos de infraestrutura. O ciclo de vida do Terraform é composto por três etapas principais: `Write`, `Plan` e `Apply`.
- Write: Definição da infraestrutura como código
- Plan: Visualização das alterações que serão realizadas
- Apply: Aplicação das alterações na infraestrutura
- Destroy: Remoção dos recursos criados

![Terraform Workflow](https://developer.hashicorp.com/_next/image?url=https%3A%2F%2Fcontent.hashicorp.com%2Fapi%2Fassets%3Fproduct%3Dterraform%26version%3Drefs%252Fheads%252Fv1.8%26asset%3Dwebsite%252Fimg%252Fdocs%252Fintro-terraform-workflow.png%26width%3D2038%26height%3D1773&w=2048&q=75)


## Providers
A conexão com os provedores de nuvem é feita através de plugins chamados de `providers`. Os providers são responsáveis por traduzir a configuração declarativa do Terraform em chamadas de API para os provedores de nuvem. O Terraform possui suporte nativo para diversos provedores de nuvem, como AWS, Azure, Google Cloud, entre outros.

> Requisitos para a vídeo aula:
> - Conta AWS
> - Terraform CLI
> - AWS CLI


## Block Types do Terraform
Os arquivos de configuração do Terraform são escritos em linguagem HCL (HashiCorp Configuration Language) e são compostos por diversos blocos de configuração. Os principais blocos de configuração do Terraform são: 
- `provider`: Configuração do provedor de nuvem
- `resource`: Definição de um recurso de infraestrutura
- `data`: Consulta de dados de um recurso existente
- `module`: Reutilização de módulos de configuração
- `variable`: Declaração de variáveis
- `output`: Exibição de valores de saída

```hcl
# Source: https://registry.terraform.io/providers/hashicorp/aws/latest
terraform {
  required_providers {
    aws = {
      source  = "hashicorp/aws"
      version = "5.54.1"
    }
  }
}

provider "aws" {
  # Configuration options
  region = "us-east-1"
}

# Source: https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/instance
data "aws_ami" "ubuntu" {
  most_recent = true

  filter {
    name   = "name"
    values = ["ubuntu/images/hvm-ssd/ubuntu-jammy-22.04-amd64-server-*"]
  }

  filter {
    name   = "virtualization-type"
    values = ["hvm"]
  }

  owners = ["099720109477"] # Canonical
}

resource "aws_instance" "web" {
  ami           = data.aws_ami.ubuntu.id
  instance_type = "t3.micro"

  tags = {
    Name = "HelloWorld"
  }
}

output "private_ip" {
  value = aws_instance.web.private_ip
}
```

> O código acima é um exemplo de configuração do Terraform que cria uma instância EC2 na AWS. O bloco `provider` configura o provedor de nuvem AWS, o bloco `data` consulta a última AMI do Ubuntu e o bloco `resource` cria uma instância EC2.

> O processo para a criação de recursos de infraestrutura com o Terraform envolve a escrita de um arquivo de configuração, a execução do comando `terraform init` para inicializar o diretório de trabalho, a execução do comando `terraform plan` para visualizar as alterações que serão realizadas e a execução do comando `terraform apply` para aplicar as alterações na infraestrutura.


## Funções
As funções são utilizadas para realizar operações de transformação de dados e lógica condicional no Terraform. As funções são utilizadas para formatar strings, converter tipos de dados, gerar números aleatórios, entre outras operações.
> [!TIP]
> Leia mais sobre as funções disponíveis no Terraform na documentação oficial: [Terraform Functions](https://developer.hashicorp.com/terraform/language/functions)

## Statefile

O Terraform mantém um arquivo de estado (`terraform.tfstate`) que armazena informações sobre a infraestrutura gerenciada. O arquivo de estado é utilizado para mapear os recursos de infraestrutura com os recursos declarados no código. Não é recomendado editar manualmente o arquivo de estado, pois ele é gerenciado pelo Terraform.

> O arquivo de estado do Terraform é armazenado localmente por padrão, mas também pode ser armazenado em um backend remoto, como Amazon S3, Google Cloud Storage, Azure Blob Storage, entre outros.

## Módulos

Os módulos são uma forma de reutilizar e organizar configurações do Terraform. Os módulos permitem encapsular recursos de infraestrutura em um pacote reutilizável que pode ser compartilhado e utilizado em diferentes projetos. Os módulos são compostos por blocos de configuração do Terraform e podem ser publicados no Terraform Registry para facilitar o compartilhamento e a reutilização. 

Os módulos podem ser utilizados para criar abstrações de infraestrutura, como uma aplicação web, um banco de dados, um ambiente de desenvolvimento, entre outros. Os módulos permitem definir interfaces claras e reutilizáveis para a criação de recursos de infraestrutura.

Exemplo de módulo:

```hcl
# Source: https://registry.terraform.io/modules/terraform-aws-modules/vpc/aws/latest
module "vpc" {
  source = "terraform-aws-modules/vpc/aws"

  name = "my-vpc"
  cidr = "10.0.0.0/16"

  azs             = ["eu-west-1a", "eu-west-1b", "eu-west-1c"]
  private_subnets = ["10.0.1.0/24", "10.0.2.0/24", "10.0.3.0/24"]
  public_subnets  = ["10.0.101.0/24", "10.0.102.0/24", "10.0.103.0/24"]

  enable_nat_gateway = true
  enable_vpn_gateway = true

  tags = {
    Terraform = "true"
    Environment = "dev"
  }
}
```
> Para executar e implementar o módulo é necessário executar as seguintes etapas:
> ```bash
> terraform init
> terraform plan
> terraform apply
> ```

> [!TIP]
> Leia mais sobre módulos no Terraform na documentação oficial: [Terraform Modules](https://developer.hashicorp.com/terraform/language/modules)

## Boas práticas

### Organização de código
- Organize o código em módulos reutilizáveis e mantenha uma estrutura de diretórios clara. 
  - Uma boa prática é separar os módulos em diretórios específicos e utilizar um arquivo `main.tf` para definir a configuração principal. Por exemplo:
    ```
    ├── modules
    │   ├── vpc
    │   │   ├── main.tf
    │   │   ├── providers.tf
    │   │   ├── outputs.tf
    │   ├── ec2
    │   │   ├── main.tf
    │   │   ├── variables.tf
    │   │   ├── outputs.tf
    ```
- Utilize variáveis para parametrizar a configuração e torná-la mais flexível.
  - O arquivo `variables.tf` define as variáveis de entrada do módulo.
    ```hcl
    variable "name" {
      type        = string
      description = "The name of the VPC"
    }
    ```
  - A atribuição das variáveis pode ser feita em um arquivo `.tfvars`.
    ```hcl
    name = "my-vpc"
    ```
  - O uso das variáveis é feito no arquivo `main.tf`.
    ```hcl
    resource "aws_vpc" "vpc" {
      cidr_block = var.cidr
      tags = {
        Name = var.name
      }
    }
    ```
  - `terraform apply -var-file="[name].tfvars"`
- Usando `terraform fmt` para formatar o código.

### Versionamento
- Utilize controle de versão para gerenciar o código do Terraform.
  - Utilize um sistema de controle de versão, como Git, para rastrear as alterações no código.
  - Utilize tags e releases para marcar versões específicas do código.
  - Mantenha um histórico de alterações e documente as mudanças realizadas.

## Edições Terraform

O Terraform é distribuído em várias edições, cada uma com diferentes recursos e funcionalidades. As principais edições do Terraform são:
- **Terraform OSS (Open Source Software):** A edição de código aberto do Terraform, que é gratuita e pode ser utilizada por qualquer pessoa.
- **Terraform Cloud `SaaS`:**  A plataforma de colaboração e automação do Terraform, que oferece recursos adicionais, como controle de acesso, integração contínua, armazenamento de estado remoto, entre outros.
- **Terraform Enterprise:** A edição corporativa do Terraform, que oferece recursos avançados de segurança, governança e conformidade para organizações de grande porte.


## Encerramento
Nesse módulo, foi abordado uma introdução ao Terraform `IaC`, suas funcionalidades, workflow, blocos de configuração, funções, statefile, módulos, boas práticas e edições. O Terraform é uma ferramenta poderosa para gerenciar infraestrutura como código e automatizar a criação e gerenciamento de recursos de infraestrutura em diversos provedores de nuvem. 