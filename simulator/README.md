# Imersão Full Stack & FullCycle - Codelivery

## Descrição

Repositório do front-end feito com Golang (Backend)

**Importante**: A aplicação do Apache Kafka deve estar rodando primeiro.

## Configurar /etc/hosts

A comunicação entre as aplicações se dá de forma direta através da rede da máquina.
Para isto é necessário configurar um endereços que todos os containers Docker consigam acessar.

Acrescente no seu /etc/hosts (para Windows o caminho é C:\Windows\system32\drivers\etc\hosts):
```
127.0.0.1 host.docker.internal
```
Em todos os sistemas operacionais é necessário abrir o programa para editar o *hosts* como Administrator da máquina ou root.

## Rodar a aplicação

Execute os comandos:

```
docker-compose up -d
# Entrar no container
docker-compose exec app bash
# Rodar a aplicação Golang
go run main.go
```

### Para Windows 

Lembrar de instalar o WSL2 e Docker. Vejo o vídeo: [https://www.youtube.com/watch?v=usF0rYCcj-E](https://www.youtube.com/watch?v=usF0rYCcj-E) 

Siga o guia rápido de instalação: [https://github.com/codeedu/wsl2-docker-quickstart](https://github.com/codeedu/wsl2-docker-quickstart) 


up docker

docker-compose up -d      

list 

docker-compose ps   

Enter into container

docker exec -it simulator bash

#Gerenciador de pacotes do GO inicializar

go mod init github.com/codeedu/imersaofsfc2-simulator

#O projeto possui dois dockers compose, do apache-kafka e da aplicação

cd apache-kafka && docker-compose up -d
docker exec -it kafka_kafka_1 bash
kafka-console-consumer --bootstrap-server=localhost:9092 --topic=readtest