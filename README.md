# Linux

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
NOME_DA_VARIAVEL="/PATH/"
```

Exemplo:
```
JAVA_HOME="/usr/lib/jvm/jdk-15/"
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

Exportar para o PATH

```
export NOME_DA_VARIAVEL="/PATH/"
export PATH=$PATH:$NOME_DA_VARIAVEL
```

Exemplo:
```
export JAVA_HOME="/usr/lib/jvm/jdk-15/"
export PATH=$PATH:$JAVA_HOME/bin
```

Com isso, já é possível utilizar os comandos Java no terminal do Linux

```
java -version
```

