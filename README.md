# Checkpoint 2 Microsservices | FIAP

## Pré-requisitos

- Java 17+
- Docker
- Acesso a internet
- Acesso ao Docker Hub

## Instalação

Para conseguir instalar o projeto corretamente, siga os passos abaixo.

1 - Dê o git clone no seguinte repositório:

```
git clone https://github.com/BrunoBenassi/fiap-checkpoint2-microsservice.git
```

2 - Entre no PowerShell, CMD ou sua CLI de preferência, entre no diretório do projeto e com o seu usuário docker logado (docker login) crie a imagem no Docker com o seguinte comando:

```
docker build -t brunobenassi/fiap-checkpoint2:latest .
```

3 - Para darmos upload de imagem para o Docker Hub

```
docker push brunobenassi/fiap-checkpoint2:latest
```

4 - Agora, vamos utilizar o um comando docker para executar a aplicação que criamos no docker hub com o profile "dev" - H2

```
docker run -d -p 8080:8080 -e PROFILE=dev brunobenassi/fiap-checkpoint2 .
```

Pronto, agora basta entrar no projeto em sua IDE de preferência, rodar a aplicação em "dev" e entrar no link:

http://localhost:8080/h2-console

Por fim, altere as seguintes informações:

- Username: sa
- Password: password
- Url: jdbc:h2:mem:testdb

  ![image](https://github.com/BernardoAssad/fiap-checkpoint2-microsservice/assets/53319308/f30ddea3-dad7-41e2-adde-f40c16ff90c0)


Comando docker para executar a aplicação a partir do docker hub com o profile "stg" - MySQL

```
docker run -d -p 8080:8080 -e PROFILE=stg fiap-checkpoint2 .
```

Por fim, altere as seguintes informações:

- Username: root
- Password: root_pwd
- Url: jdbc:mysql://localhost:3306/rh?createDatabaseIfNotExist=true

Comando docker para executar a aplicação a partir do docker hub com profile "prd" - Oracle SQL:

```
docker run -d -p 8080:8080 -e PROFILE=prd fiap-checkpoint2 .
```

Por fim, altere as seguintes informações:

- Username: pf1524
- Password: password
- Url: jdbc:oracle:thin:@oracle.fiap.com.br:1521:orcl


## Valor agregado ao estudo

- Implementar múltiplos profiles de execução de código com Docker
- Acesso a diversos Banco de Dados com Spring Boot e suas dependências.

## Dependências usadas no Spring Boot:

![image](https://github.com/BernardoAssad/fiap-checkpoint2-microsservice/assets/53319308/9375efad-532a-40d0-87b1-13eeba0e0cc8)

## Desenvolvido por:

- Bernardo Assad | bernardoassad04@gmail.com
- Bruno Benassi | brunobenassi26@gmail.com
- Henry Pinheiro | henrypin0710@gmail.com

## Redes:

GitHub - https://github.com/BrunoBenassi
DockerHub - https://hub.docker.com/u/brunobenassi


