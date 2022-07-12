# Aula-3
## Instalando o Docker?

Você tem várias maneiras de instalar o Docker no seu sistema operacional, nesta Aula iremos abordar a instalação no sistema Ubuntu Linux.

 - [Instalando Docker para MacOS](https://docs.docker.com/desktop/mac/install/)
 - [Instalando Docker para Windows](https://docs.docker.com/desktop/windows/install/)
 - [Instalando Docker para Linux](https://docs.docker.com/desktop/linux/install/)

1. Atualize o indice de pacotes do apt
```bash
sudo apt-get update
```
```bash
sudo apt-get install \
    ca-certificates \
    curl \
    gnupg \
    lsb-release
```

2. Adicione a chave GPG Oficial da Docker
```bash
sudo mkdir -p /etc/apt/keyrings
```
```bash
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
```

3. Configure o repositorio
```bash
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
  $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```

4. Atualize o indice de pacotes do apt e instale o Docker
```bash
sudo apt-get update
```
```bash
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-compose-plugin
```

5. Verifique se a instalação ocorreu corretamente:
```bash
docker version
```
6. Rode o Docker Hello World para validar sua instalação:
```bash
docker run hello-world
```
O resultado esperado do comando acima é esse: 
```text
Unable to find image 'hello-world:latest' locally
latest: Pulling from library/hello-world
2db29710123e: Pull complete
Digest: sha256:13e367d31ae85359f42d637adf6da428f76d75dc9afeb3c21faea0d976f5c651
Status: Downloaded newer image for hello-world:latest

Hello from Docker!
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
```



>Referência: https://docs.docker.com/engine/install/ubuntu/#install-using-the-repository