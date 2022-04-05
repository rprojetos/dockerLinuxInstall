# Instalação e uso do docker no Linux (Ubuntu 20.04)

## 1-Instalando o docker:

1.1-Atualize sua lista existente de pacotes:
- [x] \$ sudo apt update
  
1.2-Instalar pacotes pré-requisito que deixam o apt usar pacotes pelo HTTPS
- [x] \$ sudo apt install apt-transport-https ca-certificates curl software-properties-common

1.3-Adicione a chave GPG para o repositório oficial do Docker no seu sistema:
- [x] \$ curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -

1.4-Adicione o repositório do Docker às fontes do APT:
- [x] \$ sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu focal stable"

1.5-Atualize o banco de dados do pacote com os pacotes do Docker do recém adicionado repositório:
- [x] \$ sudo apt update

1.6-Certifique-se de que você está prestes a instalar do repositório do Docker ao invés do repositório padrão do Ubuntu:
- [x] \$ apt-cache policy docker-ce

> Saida(Deverá ser parecida com essa):
docker-ce:
  Installed: (none)
  Candidate: 5:20.10.14~3-0~ubuntu-focal
  Version table:
     5:20.10.14~3-0~ubuntu-focal 500
        500 https://download.docker.com/linux/ubuntu focal/stable amd64 Packages

1.7-instale o Docker:
- [x] \$ sudo apt install docker-ce

1.8-O Docker deve agora ser instalado, o daemon iniciado e o processo habilitado a iniciar no boot. Verifique se ele está funcionando:
- [x] $ sudo systemctl status docker

>Saida:
● docker.service - Docker Application Container Engine
     Loaded: loaded (/lib/systemd/system/docker.service; enabled; vendor preset: enabled)
     Active: active (running) since Tue 2022-04-05 06:22:19 -03; 45s ago
TriggeredBy: ● docker.socket
       Docs: https://docs.docker.com
   Main PID: 8981 (dockerd)
      Tasks: 13
     Memory: 28.0M
     CGroup: /system.slice/docker.service
             └─8981 /usr/bin/dockerd -H fd:// --containerd=/run/containerd/containerd.sock


## 2-Executando o Comando Docker Sem Sudo (Opcional)


2.1-Adicione seu nome de usuário no grupo docker:
- [x] \$ sudo usermod -aG docker ${USER}

2.2-Para inscrever o novo membro ao grupo, digite:
- [x] \$ su - ${USER}

2.3-Confirme que seu usuário agora está adicionado ao grupo docker digitando:
- [x] \$ id -nG

> Saida:
rprojetos adm cdrom sudo dip plugdev lpadmin lxd sambashare docker

## 3-Verificando/testando a instalação:

3.1-Verificando a instalação:
- [x] \$ docker info

>Saida:
Client:
 Context:    default
 Debug Mode: false
 Plugins:
  app: Docker App (Docker Inc., v0.9.1-beta3)
  buildx: Docker Buildx (Docker Inc., v0.8.1-docker)
  scan: Docker Scan (Docker Inc., v0.17.0)
Server:
 Containers: 0
  Running: 0
  Paused: 0
  Stopped: 0
 Images: 0
 Server Version: 20.10.14

3.2-Testando a instalação (Hello World):
- [x] \$ docker run hello-world

>Saida:
    Unable to find image 'hello-world:latest' locally
    latest: Pulling from library/hello-world
    2db29710123e: Pull complete 
    Digest: sha256:bfea6278a0a267fad2634554f4f0c6f31981eea41c553fdf5a83e95a41d40c38
    Status: Downloaded newer image for hello-world:latest
    `Hello from Docker!`
    This message shows that your installation appears to be working correctly.
    To generate this message, Docker took the following steps:
    1. The Docker client contacted the Docker daemon.
    2. The Docker daemon pulled the "hello-world" image from the Docker Hub.
        (amd64)
    3. The Docker daemon created a new container from that image which runs the
        executable that produces the output you are currently reading.
    4. The Docker daemon streamed that output to the Docker client, which sent it
        to your terminal.
    To try something more ambitious, you can run an Ubuntu container with:
    $ docker run -it ubuntu bash
    Share images, automate workflows, and more with a free Docker ID:
    https://hub.docker.com/
    For more examples and ideas, visit:
    https://docs.docker.com/get-started/

## 4-Ref:
[digitalocean](https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-on-ubuntu-20-04-pt)