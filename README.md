# Linux

## Gerenciador de Pacotes

### Debian

#### Advanced Packaging Tool (APT)

Software que permite o gerenciamento de pacotes de software em distribuições Linux Debian e suas variantes.

Contém uma série de ferramentas usadas no gerenciamento dos pacotes, tais como o apt-get e o apt-cache.

Para funcionar, o APT usa um arquivo que lista as "fontes" de onde ele obterá os pacotes. Esse arquivo é o /etc/apt/sources.list.

Instalar um programa:

```
apt-get install tree
```

Apagar todos os pacotes baixados e já instalados: 

```
apt-get clean
```

Apagar pacotes que não podem ser mais baixados:

```
apt-get autoclean
```

Apagar pacotes órfãos (dependências de softwares já removidos):

```
apt-get autoclean
```

Apagar pacotes:

```
apt-get remove PACOTE
```

Remover pacotes e arquivos de configuração:

```
apt-get --purge remove PACOTE
```

## Permissões 

Com o comando listar mais a flag l é possível ver as permissões de um determinado arquivo ou diretório:

```
ls -l 
```

Por exemplo:

```
drwxr-xr-x proprietario grupo
```

Primeiro caractere representa:

```
d = diretório
- = arquivo comum de usuário
c = arquivo de caratere
b = arquivo de bloco
l = link 
```

Os demais caracteres representam as permissões de três conjuntos:

No exemplo anterior: 

```
Proprietário  Grupo   Outros
rwx           r-x     r-x
```

```
r = read (leitura)
w = write (escrita)
x = execution (execução)
- = sem premissão
```


O comando chmod (change mode)

Modo de permissão octal


```
chmod [permissões] [arquivo/diretório]

Execução = 1
Escrita = 2
Leitura = 4

rwx
111		1 = ligado / 0 = desligado

--x
001 = 1

-w-
010	= 2

r--
100 = 4

rw-
110 = 4 + 2 = 6

rwx
111 = 4 + 2 + 1

```

Alguns exemplos: 

```
Para permissão de escrita, leitura e execução para o proprietário:
chmod 700 [nome_arquivo/diretório]

Para permissão de escrita, leitura e execução para o proprietário e grupo:
chmod 770 [nome_arquivo/diretório]

Para permissão de leitura para o proprietário e grupo:
chmod 400 [nome_arquivo/diretório]
```

## Instalação de programas

### Instação pelo gerenciador de pacote 

#### Debian/Ubuntu 

Para instalar a última versão estável

```
apt-get install NOME_DO_PROGRAMA
```

Exemplo:
```
apt-get install git
```

#### Fedora

Para instalar a última versão estável

```
yum install NOME_DO_PROGRAMA
```

Exemplo:
```
yum install git
```


### Instalando um programa .tar.gz

Descompactando e copiando para a pasta padrão de programas instalados

Exemplo:
```
tar -C /usr/local -xzf go1.15.2.linux-amd64.tar.gz
```

## Variáveis de ambiente

### Ubuntu

Mostrar todas as variáveis de ambiente

```
printenv
```

Criar uma nova variável

```
vim /etc/profile
```

Adicionar às variáveis de ambiente no PATH

Exemplo:
```
export JAVA_HOME=/usr/lib/jvm/jdk-15/
export GOROOT=/usr/local/go/
export PATH=$PATH:$JAVA_HOME/bin:$GOROOT/bin
```

Mostrar

```
echo $NOME_DA_VARIAVEL
```

Exemplo:
```
echo $JAVA_HOME
```

```
printenv NOME_DA_VARIAVEL
```

```
printenv JAVA_HOME
```

Com isso, já é possível utilizar os comandos Java e Go no terminal do Linux

```
java -version

go env
```

