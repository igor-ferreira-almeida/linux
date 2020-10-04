# Linux

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

```
chmod [permissões] [nome_arquivo/diretório]
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

