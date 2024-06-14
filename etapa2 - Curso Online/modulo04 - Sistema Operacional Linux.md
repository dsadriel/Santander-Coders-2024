# Sistema Operacional Linux

## Introdução ao Linux
Linux é um sistema operacional de código aberto baseado em UNIX, criado por Linus Torvalds em 1991. O Linux é um sistema operacional muito popular entre os desenvolvedores e é amplamente utilizado em servidores web e supercomputadores. O Linux é conhecido por sua estabilidade, segurança e flexibilidade. Possui uma grande variedade de distribuições, como Ubuntu, Fedora, Debian, CentOS, entre outras.

### GUI vs CLI
O Linux oferece duas interfaces principais: a GUI (Graphical User Interface) e a CLI (Command Line Interface). A GUI é uma interface gráfica que permite que os usuários interajam com o sistema operacional usando o mouse e o teclado. A CLI é uma interface de linha de comando que permite que os usuários interajam com o sistema operacional digitando comandos.

## Introdução ao Terminal/Bash

### O que é um terminal?
Um terminal é uma interface de linha de comando que permite que os usuários interajam com o sistema operacional digitando comandos. 

### O que é o Bash?
Bash é um shell de linha de comando para sistemas operacionais baseados em UNIX, como Linux e macOS. O bash é um interpretador de comandos que permite que os usuários interajam com o sistema operacional digitando comandos.

```bash
cat /etc/issues
```

## Executando os primeiros comandos
`~` representa o diretório home do usuário.
```bash
cat # Concatenate and display files
pwd # Print Working Directory
ls # List Directory Contents
cd # Change Directory 
##### - (hífen) representa o diretório anterior
##### . (ponto) representa o diretório atual
##### .. (dois pontos) representa o diretório pai
clear # Clear the terminal screen
```

## Identificando e criando, apagando e movendo arquivos e diretórios
```bash
touch # Create an empty file
mkdir # Make Directory 
##### -p cria diretórios aninhados
tree # List contents of directories in a tree-like format
mv # Move files or directories can also be used to rename files or directories

rm # Remove files or directories
##### -d remove empty directories
##### -r remove directories and their contents recursively
##### Atenção ao usar o comando rm, pois ele remove permanentemente os arquivos e diretórios
cp # Copy files or directories
##### -u copy only when the source file is newer than the destination file or when the destination file is missing
##### -p preserve the file attributes
```

## Instalando programas e movendo arquivos e diretórios
> No Linux os programas são instalados através de pacotes, que são arquivos que contêm os arquivos binários, bibliotecas e outros recursos necessários para a instalação de um programa.

### Gerenciadores de pacotes
Os gerenciadores de pacotes são ferramentas que facilitam a instalação, atualização e remoção de programas no Linux. Alguns dos gerenciadores de pacotes mais populares são: 
- `apt` (Advanced Package Tool) - usado em distribuições baseadas em Debian, como Ubuntu.
- `yum` (Yellowdog Updater Modified) - usado em distribuições baseadas em Red Hat, como CentOS.
- `dnf` (Dandified Yum) - usado em distribuições baseadas em Red Hat, como Fedora.
- `zypper` - usado em distribuições baseadas em SUSE, como openSUSE.

### Instalando programas
```bash
apt search # Search for packages
apt install # Install packages
##### -y assume yes as the answer to all prompts and run non-interactively
##### -f attempt to correct a system with broken dependencies in place
apt remove # Remove packages
apt purge # Remove packages and their configuration files
apt update # Update the package list
apt upgrade # Upgrade the installed packages
```

## Visualizando o conteúdo e editando arquivos
Os editores de texto são ferramentas que permitem visualizar e editar arquivos de texto no Linux. Alguns dos editores de texto mais populares são:
- `nano` - um editor de texto simples e fácil de usar.
- `vim` - um editor de texto avançado com muitos recursos e comandos.

### VIM
O vim é um editor de texto avançado que oferece muitos recursos e comandos. Alguns dos comandos mais comuns do vim são:
- `i` - entrar no modo de inserção.
- `Esc` - sair do modo de inserção.
- `:w` - salvar o arquivo.
- `:q` - sair do vim.
- `:wq` - salvar e sair do vim.
- `:help` - exibir a ajuda do vim.
- `u` - desfazer a última alteração.
- `Ctrl + r` - refazer a última alteração desfeita.

## Comprimindo arquivos e diretórios
A compressão de arquivos e diretórios é uma técnica usada para reduzir o tamanho dos arquivos e economizar espaço em disco. Alguns dos formatos de compressão mais comuns são:
- `tar` - um utilitário de arquivamento que cria arquivos tar.
- `gzip` - um utilitário de compressão que compacta arquivos usando o algoritmo de compressão gzip.

### TAR
O tar é um utilitário de arquivamento que cria arquivos tar. Alguns dos comandos mais comuns do tar são:
- `tar -cvf` - criar um arquivo tar.
- `tar -xvf` - extrair um arquivo tar.
- `tar -tvf` - listar o conteúdo de um arquivo tar.
- `tar -zcvf` - criar um arquivo tar comprimido com gzip.
- `tar -zxvf` - extrair um arquivo tar comprimido com gzip.

## Um pouco sobre Shell Script e Permissões

### Shell Script
Shell script é uma sequência de comandos que são executados em um shell de linha de comando. Os scripts de shell são usados para automatizar tarefas repetitivas e complexas no Linux. Os scripts de shell são escritos em um arquivo de texto com a extensão `.sh` e podem ser executados usando o shell de linha de comando.

```bash
#!/bin/bash
# This is a comment
echo "Hello, $1!" # Print a message with the first argument
```


### Permissões
As permissões de arquivos e diretórios no Linux são usadas para controlar quem pode acessar, modificar e executar arquivos e diretórios. As permissões são divididas em três grupos: proprietário, grupo e outros. Cada grupo tem permissões de leitura, gravação e execução.

Um exemplo de permissões de arquivo:
```bash
-rw-r--r-- 1 user group 0 Jan 1 00:00 file.txt
```
Neste exemplo, o arquivo `file.txt` tem as seguintes permissões:
- O proprietário tem permissão de leitura e escrita.`rw-`
- O grupo tem permissão de leitura. `r--`
- Outros usuários têm permissão de leitura. `r--`
    
```bash
chmod # Change file permissions
##### + adiciona permissões
##### - remove permissões
##### = define permissões
##### r (read) - permissão de leitura
##### w (write) - permissão de escrita
##### x (execute) - permissão de execução
##### u (user) - proprietário do arquivo
##### g (group) - grupo do arquivo
##### o (others) - outros usuários
##### a (all) - todos os usuários
```

Um de comando para permitir a execução de um arquivo:
```bash
chmod +x script.sh
```


## Procurando Arquivos e Diretórios
```bash
find search/dir # Search for files and directories
##### -name search by name
##### -type search by type (f - file, d - directory)
##### -mtime search by modification time
```