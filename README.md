
## Guia de Setup VPS usando Traefik + Portainer
Eu como uma pessoa que nunca tinha usado docker ou configurado uma VPS ou um proxy reverso, tive alguma dificuldade de juntar tudo isso e fazer funcionar.

Então esse repositório é uma foma de documentar e guiar esse passo a passo na criação de um setup de "dockerização" numa VPS.

### 1. Atualize os pacotes apt
```http
  sudo apt-get update && apt-get upgrade
```

### 2. Faça a instalação do docker
Documentação oficial [aqui](https://docs.docker.com/engine/install/).

### 3. Configuração inicial
Com tudo instalado e atualizado, vamos começar.
Criando rede docker:
```http
  docker network create traefik
```

Criar senha de acesso da interface traefik:
```http
  sudo apt-get install apache2-utils
```
```http
  htpaasswd -nb admin SUA_SENHA
```

### 4. Configuração Pastas e Arquivos
Aqui vamos configurar as pastas necessárias para o traefik funcionar.
A estrutura de pastas é:
```http
  home/
    └── docker/
        │── docker-compose.yml
        └── traefik/
            └── acme.json
```

Crie o arquivo "acme.json" e dê permissão 600:
```http
  touch acme.json
```
```http
  chmod 600 acme.json
```

