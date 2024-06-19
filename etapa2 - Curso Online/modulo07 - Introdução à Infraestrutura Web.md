# Introdução à Infraestrutura Web
> André Ferreira, professor de Infraestrutura de Web da ADA

## Introdução à infraestrutura web

A infraestrutura web é o conjunto de recursos necessários para hospedar e disponibilizar aplicações web. Esses recursos incluem servidores, sistemas operacionais, bancos de dados, servidores web, linguagens de programação, protocolos de comunicação, entre outros.

## Características da infraestrutura web
- **Escalabilidade**: capacidade de aumentar ou diminuir a capacidade de processamento e armazenamento conforme a demanda.
- **Disponibilidade**: garantia de que a aplicação estará disponível e acessível para os usuários.
- **Segurança**: proteção dos dados e informações contra acessos não autorizados.
- **Desempenho**: garantia de que a aplicação responda de forma rápida e eficiente.
- **Flexibilidade**: capacidade de adaptar a infraestrutura às necessidades da aplicação.
- **Descentralização**: distribuição dos recursos em diferentes servidores e locais geográficos.

A infraestrutura física é composta por servidores, roteadores, switches, cabos, entre outros equipamentos. A infraestrutura virtual é composta por máquinas virtuais, contêineres, serviços de nuvem (AWS, Azure, etc.), entre outros recursos.

## Sistemas operacionais para servidores web

Os sistemas operacionais para web servers são responsáveis por gerenciar os recursos do servidor, como processamento, memória, armazenamento e rede. Alguns dos sistemas operacionais mais utilizados para servidores web são:
- **Linux**: distribuições como Ubuntu, CentOS, Debian, entre outras.
- **Windows Server**: sistema operacional da Microsoft para servidores.
- **Unix**: sistemas como FreeBSD, OpenBSD, entre outros.

### O que deve ser considerado ao escolher um sistema operacional para servidores web?
- **Compatibilidade com a aplicação**: verificar se o sistema operacional é compatível com a aplicação a ser hospedada.
- **Segurança**: avaliar a segurança do sistema operacional e a disponibilidade de atualizações de segurança.
- **Desempenho**: verificar o desempenho do sistema operacional em relação à aplicação.
- **Facilidade de administração**: considerar a facilidade de administração e configuração do sistema operacional.

## Web Servers
Os são softwares responsáveis por receber as requisições dos clientes (navegadores) e retornar as respostas correspondentes. Alguns dos web servers mais utilizados são:
- **Apache**: servidor web de código aberto amplamente utilizado.
- **Nginx**: servidor web de alto desempenho e baixo consumo de recursos.
- **IIS (Internet Information Services)**: servidor web da Microsoft para sistemas Windows.


## Bancos de dados para infraestrutura web

> Usuário -> Navegador -> Web Server -> Banco de Dados

Os bancos de dados são responsáveis por armazenar e gerenciar os dados das aplicações web. Existem diferentes tipos de bancos de dados, como bancos de dados relacionais (SQL) e bancos de dados NoSQL. Alguns dos bancos de dados mais utilizados são:
- **MySQL**: banco de dados relacional de código aberto.
- **PostgreSQL**: banco de dados relacional de código aberto com recursos avançados.
- **MongoDB**: banco de dados NoSQL orientado a documentos.
- **Redis**: banco de dados NoSQL de chave-valor de alto desempenho.

### Bancos de dados relacionais (SQL)
Os bancos de dados relacionais são baseados no modelo relacional e utilizam a linguagem SQL (Structured Query Language) para consultar e manipular os dados. As tabelas dos bancos de dados relacionais são organizadas em linhas e colunas, e as relações entre as tabelas são definidas por chaves estrangeiras. Os bancos de dados são divididos em entidades e relacionamentos.

### Bancos de dados NoSQL
Os bancos de dados NoSQL são baseados em modelos de dados não relacionais e são utilizados em aplicações que requerem escalabilidade e flexibilidade. Os bancos de dados NoSQL são conhecidos por sua capacidade de armazenar dados não estruturados, sem esquema fixo e com alta disponibilidade. Os bancos de dados NoSQL são utilizados em aplicações que requerem alta velocidade de leitura e gravação, como aplicações de Big Data, IoT (Internet das Coisas) e aplicações em tempo real.


## Linguagens de programação para web

> - **HTML (HyperText Markup Language)**: linguagem de marcação utilizada para criar páginas web.
> - **CSS (Cascading Style Sheets)**: linguagem de estilização utilizada para definir a aparência das páginas web.
- **JavaScript**: linguagem de programação utilizada para adicionar interatividade e dinamismo às páginas web. Pode ser executada no navegador (frontend) ou no servidor (backend).
- **PHP (Hypertext Preprocessor)**: linguagem de programação utilizada para desenvolver aplicações web e sistemas web. Pode ser integrada com HTML e bancos de dados. É uma linguagem server-side.

> Além das linguagens mencionadas, existem outras linguagens de programação utilizadas no desenvolvimento web, como Python, Ruby, Java, entre outras.

## Protocolo HTTP

O protocolo HTTP (Hypertext Transfer Protocol) é o protocolo de comunicação utilizado para transferir informações na web. O HTTP define as regras de comunicação entre o cliente (navegador) e o servidor web. O HTTP é baseado no modelo requisição-resposta, onde o cliente envia uma requisição ao servidor e o servidor retorna uma resposta.

Existem diferentes métodos HTTP, como GET (obter informações), POST (enviar informações), PUT (atualizar informações), DELETE (excluir informações), entre outros. 

Existe também o protocolo `HTTPS (HTTP Secure)`, que é uma versão segura do HTTP que utiliza criptografia para proteger as informações transmitidas na web. A conexão é criptografada e autenticada, garantindo a segurança e a privacidade dos dados. Os Certificados SSL/TLS são utilizados para estabelecer a conexão segura entre o cliente e o servidor. 