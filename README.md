# Linux

## Comandos básicos

### Mostrar o diretório atual (pwd - Print Working Directory)

```
pwd 
```

### Listar (ls - Listar)

```
ls
```

#### Mostrar descrição longa, por exemplo, permissões, usuário e grupo do arquivo, etc.

```
ls -l
```

#### Mostrar também os arquivos ocultos

```
ls -a
```

### Caracteres Coringas

```
texto1.txt
texto2.txt
texto10.txt
texto100.txt
teste.txt

ls texto?.txt
texto1.txt  texto2.txt

ls texto*.txt
texto1.txt  texto2.txt  texto10.txt texto100.txt

ls *.txt
texto1.txt  texto2.txt  texto10.txt texto100.txt  teste.txt

```

### Criar diretório (mkdir - Make Directory)

```
mkdir NOME_DO_DIRETÓRIO 
```

### Apagar diretório (rmdir - Remove Directory)

```
rm NOME_DO_DIRETÓRIO 
```

Obs.: O comando ***rmdir*** só apaga diretórios vazios, para apagar diretórios com conteúdo é preciso passar uma flag que significa recursivo: 

```
rm -r NOME_DO_DIRETÓRIO 
```

### Copiar (cp - copy)

```
cp NOME_DO_ARQUIVO ENDEREÇO_NOVO 
```

#### Copiar com outro nome

```
cp NOME_DO_ARQUIVO ENDEREÇO_NOVO/NOVO_NOME
```

#### Copiar um diretório

```
cp -r NOME_DO_DIRETÓRIO ENDEREÇO_NOVO/
```

### Mover (mv - move)

```
mv NOME_DO_ARQUIVO ENDEREÇO_NOVO 
```

#### Copiar com outro nome

```
mv NOME_DO_ARQUIVO ENDEREÇO_NOVO/NOVO_NOME
```

#### Copiar um diretório

```
mv -r NOME_DO_DIRETÓRIO ENDEREÇO_NOVO/
```


### Criar arquivo vazios (touch - )

```
touch NOME_DO_ARQUIVO
```

### Apagar arquivo (rm - Remove)

```
rm NOME_DO_ARQUIVO
```

### Mostrar conteúdo de um arquivo (cat - Concatenar)

```
cat NOME_DO_ARQUIVO
```

### Compactação de Arquivos

#### tar.gz

Compactar um arquivo:

Obs.: flag -c (create) e -z (gzip)

```
tar -cz NOME_DO_DIRETÓRIO > NOME_DO_ARQUIVO_COMPACTADO.tar.gz
```

```
tar -czf NOME_DO_DIRETÓRIO NOME_DO_ARQUIVO_COMPACTADO.tar.gz
```

Descompactar um arquivo:

Obs.: flag -x (extract)

```
tar -xz < NOME_DO_ARQUIVO_COMPACTADO.tar.gz
```

```
tar -xzf NOME_DO_DIRETÓRIO
```

### Ler arquivos grandes pelo terminal

Apenas as dez linhas do começo do arquivo:

```
head NOME_DO_ARQUIVO
```

Alterar o número de linhas, por exemplo, as três primeiras linhas do arquivo: 

```
head -n 3 NOME_DO_ARQUIVO
```

Ler apenas as dez linhas finais do arquivo:

```
tail NOME_DO_ARQUIVO
```

Obs.: Outrossim, pode usar a mesma flag de número de linhas:

```
tail -n 7 NOME_DO_ARQUIVO
```

Para fazer uma leitura dinâmica com as setas do teclado: 

```
less NOME_DO_ARQUIVO
```

## Editor de Texto (vi)

```
vi NOME_DO_ARQUIVO
```

```
Setas para cima e para baixo: navegar
i = insere caracter antes
a = insere caracter depois
A = insere no final da linha
x = exclui caracter
Número + x = por exemplo, 11x exclui 11 caracteres 
dd = exclui a linha
yy = copiar uma linha, pode ser usado com número de linhas assim como o excluir
p = colar, pode ser usado com número de linhas
esc = sair do modo edição
:q = quit (sair) do editor
:w = salvar
:wq = salvar e sair do editor
```

### Navegação

```
1G = primeira linha
0 = começo da linha
$ = final da linha
G = última linha
/ = buscar palavra, apertando n é possível ir à próxima ocorrência
```




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

