# Introdução a Cloud Computing
> Daniel Vieira, Professor de DevOps da Ada

## Apresentação e histórico 
Em 2006, a Amazon Web Services (AWS) lançou o serviço de Elastic Compute Cloud (EC2), que permitia aos usuários alugar servidores virtuais para executar suas aplicações. Este foi um dos primeiros serviços de Cloud Computing a ser lançado e foi um marco importante na história da computação em nuvem.

O Cloud Computing é uma tecnologia que permite o acesso a recursos de computação, como servidores, armazenamento e redes, sob demanda pela Internet. Ele oferece uma maneira flexível e escalável de provisionar recursos de computação, permitindo que as empresas reduzam custos, aumentem a eficiência e inovem mais rapidamente.

## Cloud pública x privada e principais provedores

> ### Data Centers
> Os data centers são instalações físicas que abrigam servidores, armazenamento e redes de computadores. Eles são usados para armazenar e processar dados, executar aplicações e fornecer serviços de computação para empresas e usuários finais.

### Cloud Privada
A Cloud Privada é uma infraestrutura de computação em nuvem dedicada a uma única organização. Ela pode ser implantada em um data center local ou em um provedor de serviços de nuvem privada. A Cloud Privada oferece controle total sobre os recursos de computação, permitindo que as empresas personalizem a infraestrutura de acordo com suas necessidades específicas. Os principais provedores de Cloud Privada incluem VMware, Microsoft e IBM.

### Cloud Pública
A Cloud Pública é uma infraestrutura de computação em nuvem compartilhada por várias organizações. Ela é fornecida por provedores de serviços de nuvem, como a Amazon Web Services (AWS), Microsoft Azure e Google Cloud Platform. A Cloud Pública oferece uma maneira econômica e escalável de provisionar recursos de computação, permitindo que as empresas paguem apenas pelos recursos que usam.

> ### Hypervisors
> Os hypervisors são softwares que permitem a execução de múltiplos sistemas operacionais em um único servidor físico. Eles são usados para criar máquinas virtuais (VMs) que podem ser usadas para executar aplicações e serviços em ambientes de computação em nuvem.

### Cloud híbrida
A Cloud Híbrida é uma combinação de Cloud Pública e Cloud Privada que permite que as empresas aproveitem o melhor dos dois mundos. Ela oferece flexibilidade e escalabilidade da Cloud Pública, juntamente com o controle e segurança da Cloud Privada. A Cloud Híbrida permite que as empresas movam cargas de trabalho entre a Cloud Pública e a Cloud Privada, conforme necessário, para atender às suas necessidades de negócios.

## Modelos IaaS, PaaS, SaaS e Serverless

![Comparativo entre IaaS, PaaS e SaaS, Redhat.com, disponível em: <https://www.redhat.com/pt-br/topics/cloud-computing/iaas-vs-paas-vs-saas>. acesso em: 14 jun. 2024.](https://www.redhat.com/rhdc/managed-files/iaas-paas-saas-diagram5.1-1638x1046.png)
> Comparativo entre IaaS, PaaS e SaaS, Redhat.com, disponível em: <https://www.redhat.com/pt-br/topics/cloud-computing/iaas-vs-paas-vs-saas>. acesso em: 14 jun. 2024.

### IaaS (Infrastructure as a Service)
O IaaS é um modelo de computação em nuvem que fornece recursos de infraestrutura, como servidores virtuais, armazenamento e redes, sob demanda pela Internet. Ele permite que as empresas provisionem recursos de computação de forma flexível e escalável, sem a necessidade de investir em hardware físico. 

### PaaS (Platform as a Service)
O PaaS é um modelo de computação em nuvem que fornece uma plataforma de desenvolvimento e execução de aplicações sob demanda pela Internet. Ele permite que os desenvolvedores criem, testem e implantem aplicações de forma rápida e eficiente, sem se preocupar com a infraestrutura subjacente. 

### SaaS (Software as a Service)
O SaaS é um modelo de computação em nuvem que fornece software como um serviço sob demanda pela Internet. Ele permite que os usuários acessem e usem aplicativos baseados na web, como e-mail, CRM e colaboração, sem a necessidade de instalar ou manter o software localmente.  

### Serverless
O Serverless é um modelo de computação em nuvem que permite que os desenvolvedores criem e executem aplicações sem se preocupar com a infraestrutura subjacente. Ele permite que os desenvolvedores se concentrem na lógica de negócios da aplicação, enquanto a plataforma de computação em nuvem gerencia automaticamente a infraestrutura, escalabilidade e disponibilidade. É um tipo de PaaS que oferece uma abstração ainda maior da infraestrutura.


## Principais serviços

### IAM (Identity and Access Management)
O IAM é um serviço de gerenciamento de identidade e acesso que permite que as empresas controlem quem pode acessar seus recursos de computação em nuvem e o que eles podem fazer com esses recursos. Ele fornece recursos de autenticação, autorização e auditoria para proteger os dados e as aplicações na nuvem.

- Users: Usuários são identidades que podem acessar os recursos da AWS. Eles podem ser pessoas, sistemas ou serviços.
- Groups: Grupos são coleções de usuários que compartilham permissões comuns. Eles simplificam a atribuição de permissões a vários usuários.
- Roles: Funções são identidades temporárias que podem ser usadas por usuários, serviços ou sistemas para acessar recursos da AWS. Elas são usadas para delegar permissões temporárias a usuários ou serviços.
- Policies: Políticas são documentos JSON que definem as permissões de acesso aos recursos da AWS. Elas são anexadas a usuários, grupos ou funções para controlar o acesso aos recursos.


### EC2 (Elastic Compute Cloud) `IaaS`
O EC2 é um serviço de computação em nuvem que permite que as empresas aluguem servidores virtuais para executar suas aplicações. Ele oferece uma ampla variedade de tipos de instâncias, tamanhos e sistemas operacionais, permitindo que as empresas escolham a configuração mais adequada para suas necessidades.

- Instance: Uma instância é um servidor virtual que é executado no EC2. Ela pode ser configurada com diferentes tipos de instâncias, tamanhos e sistemas operacionais.
- AMI (Amazon Machine Image): Uma AMI é uma imagem de máquina que contém o sistema operacional, software e configurações necessárias para executar uma instância do EC2. Atualmente, a AWS oferece uma ampla variedade de AMIs prontas para uso, como por exemplo: Amazon Linux, Ubuntu, Windows Server, entre outros.
- Security Group: Um grupo de segurança é um conjunto de regras de firewall que controlam o tráfego de entrada e saída para as instâncias do EC2.

> Nesta aula foi apresentado uma rota para a criação de uma instância EC2 na AWS, com a configuração de uma AMI, tipo de instância, tamanho, grupo de segurança e chave de acesso.

### RDS (Relational Database Service) `PaaS`
O RDS é um serviço de banco de dados relacional que permite que as empresas criem, gerenciem e dimensionem bancos de dados na nuvem. Ele oferece suporte a vários motores de banco de dados, como MySQL, PostgreSQL, Oracle e SQL Server, permitindo que as empresas escolham o banco de dados mais adequado para suas aplicações.

### DynamoDB `PaaS`
O DynamoDB é um serviço de banco de dados NoSQL totalmente gerenciado que oferece desempenho rápido e escalabilidade automática. Ele é projetado para aplicações que requerem armazenamento de dados de baixa latência e alta disponibilidade, como jogos, aplicativos móveis e IoT.

### S3 (Simple Storage Service) `IaaS`
O S3 é um serviço de armazenamento de objetos (arquivos) que permite que as empresas armazenem e recuperem grandes quantidades de dados na nuvem. Ele oferece escalabilidade ilimitada, alta durabilidade e baixo custo de armazenamento, tornando-o ideal para armazenar dados, backups, arquivos de mídia e conteúdo estático.

## Arquitetura para Cloud

### Well-Architected Framework
O Well-Architected Framework é um conjunto de práticas recomendadas para projetar e implantar arquiteturas de nuvem seguras, eficientes e de alto desempenho. Ele fornece orientações sobre como projetar sistemas na nuvem que atendam aos requisitos de segurança, confiabilidade, desempenho e eficiência operacional.
- Pilar Excelência operacional
- Pilar Segurança
- Pilar Confiabilidade
- Pilar Eficiência de performance
- Pilar Otimização de custos
- Pilar Sustentabilidade


### Auto Scaling
O Auto Scaling é um recurso que permite que as empresas ajustem automaticamente a capacidade de computação com base na demanda de tráfego. Ele ajuda a garantir que as aplicações sejam escaláveis, resilientes e eficientes, permitindo que as empresas reduzam custos e melhorem a experiência do usuário.


Keywords: Escalabilidade, Elasticidade, Tolerância a falhas, Segurança, Eficiência, Otimização de custos, Sustentabilidade.

## Introdução à infraestrutura como código

A infraestrutura como código (IaC) é uma prática que envolve a automação da infraestrutura de computação usando código. Ela permite que as empresas definam, provisionem e gerenciem recursos de computação de forma programática, em vez de manualmente. A IaC oferece uma maneira eficiente e escalável de implantar e gerenciar infraestruturas de nuvem, permitindo que as empresas reduzam custos, realizem auditoria, aumentem a eficiência e acelerem a inovação.

### Principais ferramentas de IaC
- Terraform `Agnóstico`
- AWS CloudFormation 
- Azure Resource Manager
- Google Cloud Deployment Manager

### Terraform
O Terraform é uma ferramenta de IaC desenvolvida pela HashiCorp que permite que as empresas definam e provisionem infraestruturas de nuvem usando código. É uma ferramenta agnóstica de nuvem que suporta vários provedores de nuvem, como AWS, Azure e Google Cloud Platform. O Terraform usa uma linguagem declarativa chamada HashiCorp Configuration Language (HCL) para descrever a infraestrutura como código.

![](https://miro.medium.com/v2/resize:fit:903/1*Sxy537yBZltTATy-4-wJfQ.png)

> Na AWS é utilizada o CloudFormation, que é uma ferramenta nativa da AWS para a criação de recursos na nuvem. O CloudFormation usa um formato de modelo JSON ou YAML para descrever a infraestrutura como código. Keywords: Stack, Template, Resource, 
Output.
> - A stack é um conjunto de recursos que são criados e gerenciados juntos.
> - Um template é um arquivo JSON ou YAML que descreve a infraestrutura como código.
> - Um recurso é um componente da infraestrutura, como uma instância EC2, um banco de dados RDS ou um bucket S3.
> - Um output é um valor que é retornado após a criação de um stack, como o endereço de um servidor ou o nome de um bucket.

## Introdução ao deployment em Cloud e esteiras de CI/CD

### CI/CD (Continuous Integration/Continuous Deployment)
O CI/CD é uma prática de desenvolvimento de software que envolve a automação do processo de integração, teste e implantação de código. Ele permite que as empresas entreguem software de forma rápida, segura e confiável, acelerando o ciclo de desenvolvimento e melhorando a qualidade do software.

### Esteiras de CI/CD
Uma esteira de CI/CD é um conjunto de ferramentas e práticas que automatizam o processo de integração, teste e implantação de código. Ela permite que as empresas criem, testem e implantem software de forma eficiente e escalável, reduzindo erros, melhorando a qualidade e acelerando a entrega de software.

![](https://d1.awsstatic.com/products/codepipeline/Product-Page-Diagram_AWS-CodePipeline.4a1bea38d3c8d3b2c1384dd0a7d2a858f4350471.jpg)
>  Exemplo de uma esteira de CI/CD na AWS usando o AWS CodePipeline


> Na aula foi apresentado um exemplo criação de Pipeline usando o AWS CodePipeline para criar uma esteira de CI/CD que integra o GitHub, o AWS CodeBuild e o AWS CodeDeploy para automatizar o processo de integração, teste e implantação de código na AWS. É importante lembrar de configurar as permissões do IAM para que as ferramentas possam se comunicar entre si.

## Introdução à segurança em Cloud

### Segurança física e lógica
A segurança em nuvem envolve a proteção dos recursos de computação, dados e aplicações contra ameaças físicas e lógicas. Ela inclui práticas de segurança física, como controle de acesso, monitoramento e proteção de data centers, bem como práticas de segurança lógica, como criptografia, autenticação e autorização.

### Segurança social
A segurança social envolve a proteção dos recursos de computação, dados e aplicações contra ameaças sociais, como engenharia social, phishing e roubo de identidade. Ela inclui práticas de segurança social, como treinamento de conscientização, políticas de segurança e monitoramento de atividades suspeitas.

> **Keywords:** Minimização de privilégios, Firewall, Monitoramento, Auditoria, Conformidade, Recuperação de desastres, Backup, Políticas de segurança, Treinamento de conscientização.

## Revisão geral e conclusão
- Cloud Computing é uma tecnologia que permite o acesso a recursos de computação sob demanda pela Internet.
    - Uso sob demanda de recursos de computação, como servidores, armazenamento e redes.
    - Flexibilidade e escalabilidade para provisionar recursos de computação.
    - Acesso via Internet, sem a necessidade de investir em hardware físico.

- Cloud Pública x Cloud Privada x Cloud Híbrida
    - Cloud Pública: Infraestrutura compartilhada por várias organizações.
    - Cloud Privada: Infraestrutura dedicada a uma única organização.
    - Cloud Híbrida: Combinação de Cloud Pública e Cloud Privada.

- Modelos IaaS, PaaS, SaaS e Serverless
    - IaaS: Infraescture as a Service
    - PaaS: Platform as a Service
    - SaaS: Software as a Service
    - Serverless: Modelo de computação em nuvem que oferece uma abstração da infraestrutura.

- Principais serviços de Cloud Computing
    - IAM: Identity and Access Management
    - EC2: Elastic Compute Cloud
    - RDS: Relational Database Service
    - DynamoDB: Banco de dados NoSQL
    - S3: Simple Storage Service

- Arquitetura para Cloud
    - Well-Architected Framework
    - Auto Scaling

- Infraestrutura como código
    - Prática de automação da infraestrutura de computação usando código.
    - Ferramentas: Terraform, AWS CloudFormation, Azure Resource Manager, Google Cloud Deployment Manager.

- Deployment em Cloud e esteiras de CI/CD
    - CI/CD: Continuous Integration/Continuous Deployment
    - Esteiras de CI/CD: Conjunto de ferramentas e práticas que automatizam o processo de integração, teste e implantação de código.

- Segurança em Cloud
    - Segurança física e lógica
    - Segurança social




----

TODO:
- [ ] Revisar os Roles