# Imersão Full Stack & FullCycle - Codelivery

## Descrição

Repositório do Apache Kafka (Backend) 
Com connector do elasticsearch
Arquivo com as propriedades dessa conexão
connector/elasticsearch.properties

Esse arquivo deve ser adicionado no control center do apache-kafka

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
docker-compose up
```

Quando parar os containers do Kafka, lembre-se antes de rodar o **docker-compose up**, rodar o **docker-compose down** para limpar o armazenamento, senão lançará erro ao subir novamente.

## Entrar no Bash do Apache-kafka

docker exec -it apache-kafka_kafka_1 bash

### Enviar mensagem

kafka-console-producer --bootstrap-server=localhost:9092 --topic=route.new-direction
>{"clientId":"a","routeId":"1"}


## Debug

Listar Containers 
```
docker-compose ps
```
Mostrar logs
```
docker logs kafka-connect
```

## Acessar Control Center

localhost:9021

## Acessar o Kibana/ElasticSearch

localhost:5601

### Para Windows 

Lembrar de instalar o WSL2 e Docker. Vejo o vídeo: [https://www.youtube.com/watch?v=usF0rYCcj-E](https://www.youtube.com/watch?v=usF0rYCcj-E) 

Siga o guia rápido de instalação: [https://github.com/codeedu/wsl2-docker-quickstart](https://github.com/codeedu/wsl2-docker-quickstart) 
