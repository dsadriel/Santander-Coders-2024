# Conteinerização com Docker
> Talita Bernardes, professora de DevOps da ADA

## Apresentação de containers e instalação do Docker

## O que é Docker?
O Docker é uma plataforma de código aberto que permite a criação, execução e gerenciamento de contêineres. Os contêineres são ambientes isolados e leves que permitem a execução de aplicações de forma rápida e eficiente. O Docker é amplamente utilizado no desenvolvimento de aplicações, integração contínua, entrega contínua, orquestração de contêineres e automação de infraestrutura.

## Vantagens do Docker
- **Isolamento**: os contêineres são isolados uns dos outros e do sistema operacional hospedeiro, garantindo segurança e estabilidade.
- **Portabilidade**: os contêineres são independentes do ambiente de execução, o que facilita a migração e o escalonamento das aplicações.
- **Eficiência**: os contêineres compartilham recursos do sistema operacional hospedeiro, o que reduz o consumo de recursos e melhora o desempenho.
- **Rapidez**: os contêineres são leves e rápidos de serem criados, iniciados e destruídos, o que agiliza o desenvolvimento e a implantação de aplicações.


## Comandos do Docker

Os comandos do Docker são utilizados para criar, executar, gerenciar e interagir com contêineres. Alguns dos comandos mais comuns do Docker são:
- `docker run`: cria e executa um contêiner a partir de uma imagem.
- `docker ps`: lista os contêineres em execução.
    - `docker ps -a`: lista todos os contêineres, incluindo os que estão parados.
- `docker images`: lista as imagens disponíveis no sistema.
- `docker build`: cria uma imagem a partir de um Dockerfile.
- `docker stop`: interrompe a execução de um contêiner.
- `docker rm`: remove um contêiner.
- `docker rmi`: remove uma imagem.

## Imagens no Docker

As imagens no Docker são templates de contêineres que contêm o sistema operacional, as bibliotecas, as dependências e os arquivos necessários para executar uma aplicação. As imagens são criadas a partir de um Dockerfile, que contém as instruções para construir a imagem. As imagens são armazenadas em repositórios chamados de Docker Hub, que é um registro público de imagens do Docker.

#### Dockerfile
O Dockerfile é um arquivo de configuração que contém as instruções para construir uma imagem no Docker. O Dockerfile é utilizado para automatizar o processo de criação de imagens e garantir a reprodutibilidade do ambiente de execução.

O Dockerfile é composto por diversas instruções, como:
- `FROM`: especifica a imagem base a ser utilizada.
- `WORKDIR`: define o diretório de trabalho para os comandos seguintes.
- `ENV`: define variáveis de ambiente.
- `RUN`: executa comandos durante a construção da imagem.
- `COPY`: copia arquivos e diretórios para a imagem.
- `ENTRYPOINT`: define o comando a ser executado quando o contêiner é iniciado.
- `CMD`: define o comando padrão a ser executado quando o contêiner é iniciado.
- `EXPOSE`: expõe uma porta para o contêiner.

Exemplo de Dockerfile:
```Dockerfile
FROM ubuntu:latest # Define a imagem base

WORKDIR /app # Define o diretório de trabalho

COPY . . # Copia os arquivos do diretório atual para o diretório de trabalho

RUN apt-get update && apt-get install -y python3 # Instala o Python 3

CMD ["python3", "app.py"] # Define o comando padrão
```

## Criando containers através de imagens

> Imutabilidade: a prática de criar contêineres a partir de imagens imutáveis garante a consistência e a reprodutibilidade do ambiente de execução.

Para construir uma imagem e criar um contêiner no Docker, é necessário seguir os seguintes passos:
1. Criar um Dockerfile com as instruções para construir a imagem.
2. Construir a imagem a partir do Dockerfile com o comando `docker build`.
3. Executar o contêiner a partir da imagem com o comando `docker run`.

As imagens são construídas a partir de um Dockerfile, que contém as instruções para construir a imagem. O Dockerfile define o ambiente de execução, as dependências e os comandos necessários para executar a aplicação no contêiner. Essas imagens 

## Volumes

Por padrão, os contêineres no Docker são efêmeros, ou seja, os dados são perdidos quando o contêiner é destruído. Para persistir os dados entre execuções de contêineres, é necessário utilizar volumes no Docker. Estes mecanismos de persistência de dados que permitem armazenar e compartilhar dados entre contêineres e o sistema operacional hospedeiro. 

Existem diferentes tipos de volumes no Docker, como:
- **Docker Volumes**: volumes gerenciados pelo Docker e armazenados em diretórios no sistema de arquivos do sistema operacional hospedeiro.
- **Docker Bind**: volumes que mapeiam diretórios do sistema operacional hospedeiro para diretórios no contêiner.
- **tmpfs**: volumes que armazenam dados na memória RAM do sistema operacional hospedeiro.

Exemplo de criação de um volume no Docker:
```bash
# Usando um volume do tipo Bind:
docker run -d --name my-container --mount type=bind,source=/path/on/host,target=/path/in/container my-image
```
Os arquivos armazenados no volume `/path/on/host` no sistema operacional hospedeiro são compartilhados com o contêiner no diretório `/path/in/container`.

Os volumes também possibilitam a comunicação entre contêineres, o compartilhamento de dados entre contêineres e a persistência de dados entre execuções de contêineres.


## Redes

As redes no Docker são utilizadas para conectar contêineres entre si e com o sistema operacional hospedeiro. As redes permitem a comunicação entre contêineres, o acesso à internet, o acesso a serviços externos e a exposição de portas para acesso externo. O Docker possui uma rede interna padrão que conecta os contêineres a uma rede privada interna.

Existem diferentes tipos de redes no Docker, como:
- **Bridge**: rede padrão do Docker que conecta os contêineres a uma rede privada interna. Ele cria uma resolução interna de DNS para os contêineres.
- **Host**: rede que conecta os contêineres à rede do sistema operacional hospedeiro. Ela compartilha o mesmo espaço de rede do sistema operacional.
- **Overlay**: rede que conecta contêineres em diferentes hosts para comunicação em cluster. Ela é utilizada em ambientes distribuídos e orquestradores de contêineres.

Exemplo de criação de uma rede no Docker:
```bash
docker network create my-network
# Cria uma rede chamada my-network com as configurações padrão
# Outras opções de configuração podem ser especificadas, como o driver da rede, o endereço IP e a sub-rede.
# --driver: especifica o driver da rede (bridge, host, overlay, etc.)
# --subnet: especifica o endereço IP da sub-rede
# --gateway: especifica o gateway da rede
```

> [!TIP]
> O comando `docker network ls` lista as redes disponíveis no Docker e o comando `docker inspect my-network` exibe informações detalhadas sobre a rede my-network. 

## Ecossistema de containers

> "Um contêiner sozinho não faz verão." - Talita Bernardes

O ecossistema de contêineres é composto por diversas ferramentas e tecnologias que complementam o Docker e permitem a orquestração, a automação e a gestão de contêineres em ambientes de produção. 

Um exemplo de uma aplicação web com contêineres é a combinação de um servidor web (Apache, Nginx) com um banco de dados (MySQL, PostgreSQL) em contêineres separados. Os contêineres são conectados em uma rede interna para comunicação e compartilhamento de dados.
```bash
# Exemplo de criação de contêineres para uma aplicação web com Joomla e MySQL
docker run -e MYSQL_ROOT_PASSWORD=senha --name db -v /app:/var/lib/mysql -d mysql:latest

docker run -e JOOMLA_DB_USER=root -e JOOMLA_DB_PASSWORD=senha --name joomla --link db:mysql -p 8080:80 -d joomla:php8.0
```

## Docker Compose: o que é?

O Docker Compose é uma ferramenta que permite definir e executar aplicações multi-contêiner em um único arquivo de configuração. O Docker Compose simplifica a criação, a execução e a gestão de aplicações com múltiplos contêineres, facilitando a orquestração e a automação de ambientes de desenvolvimento e produção.

O Docker Compose utiliza um arquivo de configuração chamado `docker-compose.yml` para definir os serviços, as redes, os volumes e as variáveis de ambiente da aplicação. O arquivo de configuração é composto por diversas seções, como `services`, `networks`, `volumes`, `environment`, `ports`, `depends_on`, entre outras.

Exemplo de arquivo `docker-compose.yml`:
```yaml
version: '3.8'

services:
  db:
    image: mysql:latest
    environment:
      MYSQL_ROOT_PASSWORD: senha
    volumes:
      - /app:/var/lib/mysql

  joomla:
    image: joomla:php8.0
    environment:
      JOOMLA_DB_USER: root
      JOOMLA_DB_PASSWORD: senha
    ports:
      - 8080:80
    depends_on:
      - db
```

## Docker Compose na prática

Os principais comandos do Docker Compose são:
- `docker-compose up`: cria e inicia os contêineres da aplicação.
- `docker-compose up -d`: cria e inicia os contêineres em segundo plano.
- `docker-compose down`: interrompe e remove os contêineres da aplicação.
- `docker-compose ps`: lista os contêineres da aplicação.
- `docker-compose logs`: exibe os logs dos contêineres da aplicação.
- `docker-compose exec`: executa comandos em um contêiner da aplicação.

Para executar uma aplicação multi-contêiner com o Docker Compose, é necessário seguir os seguintes passos:
1. Criar um arquivo `docker-compose.yml` com a definição dos serviços, redes, volumes e variáveis de ambiente da aplicação.
2. Executar o comando `docker-compose up` para criar e iniciar os contêineres da aplicação.
3. Acessar a aplicação em um navegador web através do endereço `http://localhost:8080`.


## Conclusão, benefícios e orquestradores

O Docker é uma ferramenta poderosa que simplifica o desenvolvimento, a implantação e a gestão de aplicações em contêineres. Os contêineres oferecem isolamento, portabilidade, eficiência e rapidez, o que facilita a criação de ambientes de desenvolvimento e produção consistentes e reprodutíveis.

Com a popularização dos contêineres, surgiram diversos orquestradores de contêineres, como o Kubernetes, o Docker Swarm e o Amazon ECS, que permitem a automação, a escalabilidade e a gestão de contêineres em ambientes de produção. Essas ferramentas facilitam a orquestração de contêineres, o balanceamento de carga, a recuperação de falhas e a escalabilidade automática de aplicações em contêineres.
