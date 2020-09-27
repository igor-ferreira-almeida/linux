# Linux

## Variáveis de ambiente

### Ubuntu

Mostrar todas as variáveis de ambiente

```
printenv
```

Criar uma nova variável

```
JAVA_HOME="/usr/lib/jvm/jdk-15/"
```

Mostrar

```
echo $JAVA_HOME
```

```
printenv JAVA_HOME
```

Exportar para o PATH

```
export JAVA_HOME="/usr/lib/jvm/jdk-15/"
export PATH=$PATH:$JAVA_HOME/bin
```

Com isso já é possível utilizar os comandos Java no terminal do Linux

```
java -version
```

