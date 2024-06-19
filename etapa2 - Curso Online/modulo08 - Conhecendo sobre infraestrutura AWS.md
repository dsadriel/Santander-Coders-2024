# Conhecendo sobre infraestrutura AWS
> Renata Alves, Instrutora DevOps da ADA

## Computação em Nuvem

Veja [Módulo 5 - Introdução a Cloud Computing](etapa2%20-%20Curso%20Online/modulo05%20-%20Introdu%C3%A7%C3%A3o%20a%20Cloud%20Computing.md) para mais informações sobre Computação em Nuvem.

## Infraestrutura Global AWS

## Regiões e Zonas de Disponibilidade
As regiões são áreas geográficas onde a AWS possui data centers. Cada região é composta por várias Zonas de Disponibilidade (AZs), que são data centers isolados e independentes dentro de uma região. As AZs são conectadas por redes de alta velocidade e baixa latência. 

## Alta Disponibilidade e outros conceitos

A Alta Disponibilidade é a capacidade de um sistema de estar disponível e acessível para os usuários, mesmo em caso de falhas ou interrupções. Para garantir a alta disponibilidade, é necessário adotar práticas como redundância, balanceamento de carga, monitoramento e recuperação de falhas.

É importante considerar os seguintes conceitos ao projetar uma infraestrutura de alta disponibilidade:
- **Redundância**: duplicação de recursos críticos para garantir a disponibilidade do sistema.
- **Balanceamento de Carga**: distribuição equilibrada do tráfego entre os servidores para evitar sobrecarga e garantir o desempenho.
- **Monitoramento**: acompanhamento contínuo do sistema para identificar possíveis falhas e problemas.
- **Recuperação de Falhas**: implementação de mecanismos de recuperação automática em caso de falhas.
- **Latência**: tempo de resposta entre a solicitação do usuário e a resposta do sistema.

## Overview AWS

A Amazon Web Services (AWS) é uma plataforma de computação em nuvem que oferece uma ampla variedade de serviços, incluindo computação, armazenamento, banco de dados, análise, inteligência artificial, Internet das Coisas (IoT), segurança, entre outros. A AWS é conhecida por sua escalabilidade, flexibilidade, segurança e confiabilidade.

> [!TIP]
> Leia mais sobre os serviços da AWS na documentação oficial: [AWS Services](https://aws.amazon.com/pt/products/)

- AWS Console: interface web para gerenciar os recursos da AWS.
- AWS CLI: interface de linha de comando para interagir com a AWS.
- AWS SDKs: kits de desenvolvimento para integrar aplicativos com os serviços da AWS.


## Provisionando um servidor na AWS?

Para provisionar um servidor na AWS, você pode utilizar o Amazon EC2 (Elastic Compute Cloud), que é um serviço de computação em nuvem que permite criar e gerenciar instâncias de servidores virtuais na AWS. Para provisionar um servidor na AWS, você precisa seguir os seguintes passos:
1. Acessar o Console da AWS e fazer login na sua conta.
2. Navegar até o serviço Amazon EC2.
3. Criar uma nova instância EC2.
4. Escolher a AMI (Amazon Machine Image) desejada.
5. Configurar as opções da instância, como tipo, tamanho, rede, segurança, etc.
6. Criar e iniciar a instância EC2.
7. Acessar a instância via SSH ou RDP.

As instâncias são classificadas em diferentes tipos com base em suas características de CPU, memória, armazenamento e rede. Alguns dos tipos de instâncias mais comuns são:
- **T2**: instâncias de uso geral com recursos balanceados.
- **M5**: instâncias de propósito geral com alto desempenho.
- **C5**: instâncias de computação otimizadas para cargas de trabalho intensivas em CPU.

### AWS Marketplace

O AWS Marketplace é uma loja online que oferece uma ampla variedade de software, serviços e soluções prontas para uso na AWS. No AWS Marketplace, você pode encontrar e adquirir aplicativos, ferramentas, serviços gerenciados, AMIs, entre outros recursos para acelerar o desenvolvimento e a implantação de aplicações na AWS.


## Balanceamento de Carga / Elastic Load Balancing

O Elastic Load Balancing (ELB) é um serviço da AWS que distribui o tráfego entre várias instâncias EC2 para garantir a alta disponibilidade e o desempenho das aplicações. O ELB oferece três tipos de balanceadores de carga:
- **Application Load Balancer (ALB)**: balanceador de carga de camada 7 que roteia o tráfego com base no conteúdo da solicitação.
- **Network Load Balancer (NLB)**: balanceador de carga de camada 4 que roteia o tráfego com base nas informações da camada de transporte.
- **Classic Load Balancer**: balanceador de carga tradicional que distribui o tráfego entre as instâncias EC2.
- **Gateway Load Balancer**: balanceador de carga de camada 3 que roteia o tráfego entre redes virtuais.

> [!TIP]
> Leia mais sobre o Elastic Load Balancing na documentação oficial: [Elastic Load Balancing](https://aws.amazon.com/pt/elasticloadbalancing/)

## Combinando balanceamento de carga com escalabilidade na AWS para obter aplicações de alta disponibilidade e redundantes

Para obter aplicações de alta disponibilidade e redundantes na AWS, é possível combinar o balanceamento de carga com a escalabilidade automática (AWS Auto Scaling). A escalabilidade automática permite ajustar automaticamente a capacidade dos recursos de acordo com a demanda, garantindo que a aplicação esteja sempre disponível e respondendo de forma eficiente.


## AWS Well-Architected Framework

Veja [Módulo 5 - Introdução a Cloud Computing](etapa2%20-%20Curso%20Online/modulo05%20-%20Introdu%C3%A7%C3%A3o%20a%20Cloud%20Computing.md) para mais informações sobre o AWS Well-Architected Framework.

## Serviço DNS / Amazon Route 53

O Amazon Route 53 é um serviço de DNS (Domain Name System) da AWS que permite registrar domínios, gerenciar zonas de DNS, rotear o tráfego de forma inteligente e monitorar a disponibilidade dos recursos. O Route 53 oferece os seguintes recursos:
- Registro de domínios: registro e gerenciamento de domínios.
- Zonas hospedadas: gerenciamento de zonas de DNS.
- Roteamento de tráfego: roteamento inteligente do tráfego para diferentes recursos.
- Monitoramento de disponibilidade: monitoramento contínuo da disponibilidade dos recursos.
