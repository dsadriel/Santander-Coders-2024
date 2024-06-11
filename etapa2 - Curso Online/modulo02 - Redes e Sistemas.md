# Redes e Sistemas

## O que são redes?
A origem das redes de computadores remonta ao final da década de 60, quando o Departamento de Defesa dos Estados Unidos (DARPA) criou a ARPANET, uma rede de computadores que interligava universidades e centros de pesquisa. A ARPANET foi a precursora da internet, que é a maior rede de computadores do mundo. 

## Infraestrutura de redes e os principais equipamentos

- *NIC - Network Interface Card:* Placa de rede como é mais conhecida, é um dispositivo de hardware que permite que um computador se conecte a uma rede. Ela é responsável por enviar e receber dados na rede.
- *Hub:* Equipamento que interconecta vários dispositivos em uma rede. Ele só trabalha com conexões do tipo broadcast, ou seja, ele envia os dados para todos os dispositivos conectados a ele.
- *Switch:* Equipamento que interconecta vários dispositivos em uma rede. Ele trabalha com conexões do tipo broadcast e conexões ponto a ponto, ou seja, ele envia os dados apenas para o dispositivo de destino. Costuma ter 24 ou 48 portas.
- *Roteador:* Equipamento que interconecta várias redes. Ele é responsável por enviar os pacotes de dados entre as redes e buscar a rota mais eficaz para isso.
- *Modem:* Equipamento que converte os sinais digitais do computador em sinais analógicos para serem transmitidos pela linha telefônica e vice-versa. Conexões podem ser feitas via cabo, fibra óptica, linha telefônica, satélite, entre outras. Em ambientes residenciais, é comum que os modems sejam integrados aos roteadores e switches.

## Cabeamento Estruturado
São padrões estabelecidos que definem como serão as organizações dos cabos de rede e seus periféricos possibilitando a melhor organização e manutenção da rede.

### Normas:
- NBR 14565:2000: Norma brasileira que estabelece os requisitos mínimos para a elaboração de projetos e instalação de cabeamento estruturado.
- ANSI/TIA 568: Norma americana que estabelece os requisitos mínimos para a elaboração de projetos e instalação de cabeamento estruturado.
- ANSI/TIA 569: Norma americana que estabelece os requisitos mínimos para a elaboração de projetos e instalação de infraestrutura de telecomunicações em edifícios comerciais.

### Tipos de cabos

#### Cabo de par trançado:
- **UTP (Unshielded Twisted Pair):** Cabo de par trançado sem blindagem. É o mais comum e barato. Este cabo é mais suscetível a interferências.
- **STP (Shielded Twisted Pair):** Cabo de par trançado com blindagem. É mais caro e mais resistente a interferências.

<img src="https://desamarrandoarede.files.wordpress.com/2012/04/preview0051.png" alt="Cabo de par trançado" height=250>

#### Cabo coaxial:
- **Cabo coaxial:** Cabo de cobre revestido por uma malha de cobre. É mais resistente a interferências e é utilizado em redes de TV a cabo. Possui isolamento de 75 ohms.

<img src="https://www.oficinadanet.com.br/imagens/post/10155/cabo-home.jpg" alt="Cabo coaxial" height=250>

#### Fibra óptica:
- **Fibra óptica:** Cabo de vidro ou plástico que transmite dados através de pulsos de luz. É mais rápido e mais resistente a interferências. É utilizado em redes de longa distância.

<img src="https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEiu4jUzhBQmpk4xMRFRMpqxIeWoWkVAeCmmeYfoMuKLfK8BOz6g0P1vAu4TDROOtjhqauduBxFYwZB2ZLmoL23D2KmnFBE-AMcwglBi2cdKqGdi4Gspth31PeFyj7jX7UWgeYlMsp3srVud/s1600/Drawing-38+Model+(1).jpg" alt="Fibra óptica" height=250>

#### Rack:
- **Rack:** Estrutura metálica que organiza e protege os equipamentos de rede. É utilizado para acomodar servidores, switches, roteadores, entre outros.


## Modelo OSI e TCP/IP

### Modelo OSI
O modelo OSI (Open Systems Interconnection) é um modelo de referência que descreve como os dados são transmitidos em uma rede de computadores. Ele é dividido em 7 camadas, cada uma com uma função específica. 
1. **Aplicação:** É a camada mais alta do modelo OSI e mais próxima do usuário. Ela abriga os protocolos de comunicação de mais alto nível, como HTTP, FTP, SSH, entre outros. 
2. **Apresentação:** Nessa camada os dados são convertidos em um formato que pode ser entendido pelo destinatário. Isso inclui a criptografia e a compressão de dados.
3. **Sessão:** É a camada responsável por estabelecer, manter e encerrar a conexão entre os dispositivos. 
4. **Transporte:** A camada de transporte é responsável por garantir que os dados sejam transmitidos de forma confiável e eficiente. Ela divide os dados em pacotes e os reagrupa no destino. Os protocolos mais conhecidos dessa camada são o TCP (Transmission Control Protocol) e o UDP (User Datagram Protocol).
> O TCP é um protocolo orientado à conexão, ou seja, ele garante que os dados sejam transmitidos de forma confiável. Já o UDP é um protocolo não orientado à conexão, ou seja, ele não garante que os dados sejam transmitidos de forma confiável.
5. **Rede:** Define como os dados são transmitidos entre dispositivos não adjacentes. Ela é responsável por rotear os *pacotes de dados* entre as redes. Nessa camada que estão os roteadores, em uso domiciliar.
6. **Enlace:** Essa camada é responsável por fragmentar os pacotes em *quadros* e transmiti-los entre dispositivos adjacentes. Ela também é responsável por detectar e corrigir erros de transmissão. Ela é dividida em duas subcamadas: a subcamada de controle de acesso ao meio (*MAC - Media Access Control*) e a subcamada de controle de erros (*LLC - Logical Link Control*).
7. **Física:** É a camada mais baixa do modelo OSI e mais próxima do meio físico. Ela é responsável por transmitir os bits de um dispositivo para outro. Ela define as características elétricas, mecânicas e funcionais do meio físico. Exemplos de meios físicos são o cabo de par trançado, o cabo coaxial e a fibra óptica. 

> Esse modelo pode ser executado da camada 1 para a camada 7 e da camada 7 para a camada 1, dependendo da necessidade. E também nem todas as camadas são utilizadas em todas as situações. 

### Modelo TCP/IP
O modelo TCP/IP (Transmission Control Protocol/Internet Protocol) é um modelo de referência que descreve como os dados são transmitidos em uma rede de computadores. Ele é dividido em 4 camadas, cada uma com uma função específica.

1. **Aplicação:** Essa camada é equivalente às camadas de aplicação, apresentação e sessão do modelo OSI.
2. **Transporte:** Essa camada é equivalente à camada de transporte do modelo OSI.
3. **Internet:** Essa camada é equivalente à camada de rede do modelo OSI.
4. **Acesso à rede:** Essa camada é equivalente às camadas de enlace e física do modelo OSI.

## IPV4 e IPV6
O termo IP (Internet Protocol) refere-se a um protocolo de comunicação que permite a comunicação entre dispositivos em uma rede. O IP é responsável por endereçar os dispositivos e rotear os pacotes de dados entre eles. Existem duas versões do IP: o IPv4 e o IPv6.

### IPV4
O IPv4 (Internet Protocol version 4) é a quarta versão do IP e é a versão mais utilizada atualmente. Ele é um protocolo de comunicação que utiliza endereços de 32 bits para endereçar dispositivos em uma rede. Isso significa que ele pode endereçar até 2^32 dispositivos, ou seja, cerca de 4 bilhões de dispositivos. Os endereços IPv4 são representados por 4 números decimais de 8 bits [0-255] separados por pontos, por exemplo, 142.251.132.14.

#### NAT
O NAT (Network Address Translation) é uma técnica que permite que vários dispositivos compartilhem o mesmo endereço IP público. Ele é muito utilizado em redes domésticas e corporativas para economizar endereços IP públicos. O NAT funciona traduzindo os endereços IP privados dos dispositivos em endereços IP públicos. Em um ambiente doméstico, o roteador é responsável por fazer essa tradução, onde os dispositivos da rede interna possuem endereços IP privados e o roteador possui um endereço IP público. Dessa forma, os dispositivos da rede interna podem acessar a internet usando o endereço IP público do roteador.

### IPV6
O IPv6 (Internet Protocol version 6) é a sexta versão do IP e é uma versão mais recente e avançada do protocolo. Ele utiliza endereços de 128 bits para endereçar dispositivos em uma rede. Isso significa que ele pode endereçar até 2^128 dispositivos, ou seja, um número muito maior do que o IPv4. Os endereços IPv6 são representados por 8 grupos de 4 dígitos hexadecimais separados por dois pontos, por exemplo, 2001:0db8:85a3:0000:0000:8a2e:0370:7334
O IPv6 ainda não é tão amplamente utilizado quanto o IPv4, mas está se tornando cada vez mais comum à medida que o IPv4 atinge seus limites de endereçamento. O motivo da migração lenta para o IPv6 é a necessidade de atualização de equipamentos e sistemas para suportar o novo protocolo e a complexidade da transição.

## Cálculo de sub rede
TODO: revisar
O cálculo de sub-redes é uma técnica utilizada para dividir uma rede em sub-redes menores. Isso é útil para segmentar uma rede em partes menores e mais gerenciáveis, melhorar a segurança e o desempenho da rede e otimizar o uso de endereços IP. O cálculo de sub-redes é feito com base no endereço IP da rede e na máscara de sub-rede. Cada sub-rede possui um intervalo de endereços IP que pode ser usado para endereçar dispositivos nessa sub-rede. 

As classes de endereços IP são divididas em cinco classes: A, B, C, D e E. As classes A, B e C são as mais comuns e são usadas para endereçar dispositivos em uma rede. As classes D e E são reservadas para fins especiais e não são usadas para endereçar dispositivos em uma rede.

|  Classe  |    Faixa de endereços de IP   |  Notação CIDR  | Número de Redes | Número de IPs | IPs por rede |
|:--------:|:-----------------------------:|:--------------:|:---------------:|:-------------:|:------------:|
| Classe A | 10.0.0.0 – 10.255.255.255     | 10.0.0.0/8     | 128             | 16.777.216    | 16.777.214   |
| Classe B | 172.16.0.0 – 172.31.255.255   | 172.16.0.0/12  | 16.384          | 1.048.576     | 65 534       |
| Classe C | 192.168.0.0 – 192.168.255.255 | 192.168.0.0/16 | 2.097.152       | 65.535        | 254          |

#### Como o cálculo é feito?
O endereço IP é analisado em binário e a máscara de sub-rede é aplicada para determinar a quantidade de bits de host e de rede. A máscara de sub-rede é uma sequência de bits que define quais bits do endereço IP são usados para identificar a rede e quais bits são usados para identificar o host. A máscara de sub-rede é representada em notação CIDR (Classless Inter-Domain Routing) e é geralmente expressa como um número que indica quantos bits da esquerda do endereço IP são usados para identificar a rede. Por exemplo, a máscara de sub-rede. 
A quantidade de host por rede é calculada subtraindo o número de bits da máscara de sub-rede do total de bits de um endereço IP. O número de redes é calculado elevando 2 à potência do número de bits da máscara de sub-rede. Por convenção, o primeiro e o último endereço IP de cada sub-rede são reservados para o endereço de rede e o endereço de broadcast, respectivamente.

## Domínios, DNS e latência

### Domínios
Os domínios são nomes que representam endereços IP na internet. Eles são usados para identificar e localizar recursos na rede, como sites, servidores de e-mail, servidores de arquivos, entre outros. Os domínios são organizados em uma hierarquia que começa com o domínio de nível superior (TLD - Top-Level Domain) e se ramifica em subdomínios.


### DNS
O DNS (Domain Name System) é um sistema de nomes de domínio que converte nomes de domínio em endereços IP. Ele é responsável por traduzir os nomes de domínio que são fáceis de lembrar em endereços IP que são usados para identificar e localizar recursos na rede. O DNS é composto por servidores de nomes que armazenam informações sobre os domínios e respondem às consultas de resolução de nomes. O servidor de nomes raiz é o servidor de nomes de nível mais alto e é responsável por encaminhar as consultas para os servidores de nomes autoritativos dos domínios. 

https://images.google.com/search pode ser separado em:
- **Protocolo:** https
- **Subdomínio:** images
- **Domínio:** google.com
- **TLD:** com
- **Subdiretório:** search

### Latência
A latência é o tempo que um pacote de dados leva para percorrer uma rede de um ponto a outro. Ela é medida em milissegundos (ms) e é influenciada por vários fatores, como a distância entre os dispositivos, a largura de banda da rede, a qualidade da conexão, a quantidade de tráfego na rede, entre outros. Uma latência baixa é desejável, pois significa que os pacotes de dados são transmitidos rapidamente e a comunicação entre os dispositivos é eficiente. Uma latência alta pode causar atrasos na comunicação e afetar a qualidade da conexão. 

#### Cache CDN
O cache CDN (Content Delivery Network) é uma rede de servidores distribuídos geograficamente que armazena cópias de conteúdo da web, como imagens, vídeos, arquivos, entre outros. Ele é usado para acelerar o carregamento de páginas da web e reduzir a latência, pois os servidores de cache estão mais próximos dos usuários finais do que os servidores de origem. Quando um usuário solicita um recurso da web, o CDN redireciona a solicitação para o servidor de cache mais próximo, que fornece o conteúdo rapidamente. Isso melhora a experiência do usuário e reduz a carga nos servidores de origem.

## Principais comandos de configuração
Os comandos de configuração são usados para configurar e gerenciar dispositivos de rede, como roteadores, switches, servidores, entre outros. Eles permitem que os administradores de rede configurem as interfaces de rede, os protocolos de roteamento, as listas de acesso, as VLANs, entre outras configurações. Alguns dos principais comandos de configuração em sistemas Windows são:

- **ipconfig:** Exibe e configura as interfaces de rede.
    - Flush DNS: `ipconfig /flushdns` - Limpa o cache DNS do sistema.
    - Renovar IP: `ipconfig /renew` - Renova o endereço IP do sistema.
    - Liberar IP: `ipconfig /release` - Libera o endereço IP do sistema.
- **ping:** Envia pacotes de dados para um dispositivo de rede e verifica a conectividade. TTL (Time To Live) é o tempo que um pacote de dados pode permanecer na rede antes de ser descartado.
- **nslookup:** Consulta servidores de nomes DNS para obter informações sobre domínios e endereços IP.
- **tracert:** Rastreia a rota que os pacotes de dados percorrem entre o dispositivo de origem e o dispositivo de destino.
- **route:** Exibe e configura a tabela de roteamento do sistema.
    - `route print` - Exibe a tabela de roteamento.
- **netstat:** Exibe informações sobre as conexões de rede, as tabelas de roteamento, as estatísticas de interface, entre outras informações.
    - `netstat -a` - Exibe todas as conexões de rede e as portas que estão sendo usadas.
    - `netstat -r` - Exibe a tabela de roteamento.

## Segurança
A segurança de rede é a proteção dos dados e dos dispositivos de rede contra ameaças, como hackers, malware, vírus, ataques de negação de serviço, entre outros. Existem várias medidas de segurança que podem ser implementadas para proteger uma rede, como firewalls, antivírus, criptografia, autenticação, entre outras. A segurança pode ser física, lógica ou de dados.

#### Firewall
O firewall é um dispositivo de segurança que monitora e controla o tráfego de rede entre uma rede privada e a internet. O firewall pode ser implementado em hardware ou software e pode ser configurado para bloquear ou permitir o tráfego com base em regras de segurança. Existem vários tipos de firewalls, como firewalls de pacotes, firewalls de estado, firewalls de aplicativos, entre outros.

#### VPN
A VPN (Virtual Private Network) é uma rede privada virtual que permite que os usuários se conectem a uma rede privada de forma segura pela internet. A VPN criptografa os dados que são transmitidos entre o dispositivo do usuário e a rede privada, protegendo a comunicação contra interceptação e espionagem. A VPN é usada para proteger a privacidade e a segurança dos dados dos usuários, especialmente em redes públicas e não confiáveis.

#### Ataques de segurança
    - DoS (Denial of Service): Ataque que visa sobrecarregar um servidor ou rede com tráfego malicioso, tornando-o inacessível para os usuários legítimos.
    - DDoS (Distributed Denial of Service): Ataque DoS que é realizado por vários dispositivos distribuídos em diferentes locais.
    - Phishing: Ataque que visa enganar os usuários para obter informações confidenciais, como senhas, números de cartão de crédito, entre outros.
    - Malware: Software malicioso que é projetado para danificar, roubar ou controlar um dispositivo ou rede.
    - Ransomware: Malware que criptografa os arquivos de um dispositivo e exige um resgate para descriptografá-los.
    - Spyware: Software malicioso que é projetado para espionar as atividades de um usuário, como digitação de teclas, navegação na web, entre outros.
    - Injeção de SQL: Ataque que explora vulnerabilidades em aplicativos da web para injetar comandos SQL maliciosos e obter acesso não autorizado ao banco de dados.

## Wireless
> Aula prática utilizando o software Cisco Packet Tracer para simular uma rede sem fio. Foi realizado de duas redes cabeadas cada uma com dois dispositivos e interconexão entre elas por meio de um roteador.