# Docker e docker compose
[CLIQUE AQUI](https://fpatrick.github.io/tutoriaisrpi/) PARA VOLTAR AO INICIO.

### O que e docker
Todos conhecemos a ideia de virtualizar um sistema operacional atraves do virtualbox ou outro servico semelhante. Basicamente o docker e a mesma coisa, mas virtualizando aplicativos ao inves de sistemas operacionais.

### Por que usar?
1. Sem dependencias. Os servicos podem precisar de bibliotecas ou terem dependencias para funcionar, assim como no windows as vezes um programa pede pra instalar o java para abrir. No linux isso e muito mais complexo, onde um servico pode precisar do python 2.6 e outro do python 2.5, com tantas versoes conflitando nem tudo pode ser tao facil manter. Dentro do container ja vem todas bibliotecas e dependencias que o servico precisa para rodar perfeitamente.

2. Instalacao. Instalar um servico pelo docker e tao simples quanto baixar um arquivo. Nada da complexidade do linux de compilar da fonte ou procurar pacotes prontos.

3. Facilidade de gerenciar. Voce pode pausar, excluir, restaurar muito facilmente qualquer servico dentro de containers de docker.

### Instalando docker

**Instalar**
```
curl -sSL https://get.docker.com | sh
```

**(Opcional) Dar permissao ao usuario padrao, para usar docker sem sudo**
```
sudo usermod -aG docker pi
```

**Verficar se funciona**
```
docker run hello-world
```
### Servico para ver e gerenciar os containers pelo navegador

O portainer e o melhor servico para visualizar e gerenciar seus containers pelo navegador. Basta instalar e acessar.

**Instalar portainer**
```
docker volume create portainer_data
docker run -d -p 8000:8000 -p 9000:9000 --name portainer --restart always -v \\.\pipe\docker_engine:\\.\pipe\docker_engine -v portainer_data:C:\data portainer/portainer
```
Agora abra o navegador e acesse: `http://enderecodoseuraspberry:9000`. Exemplo: `192.168.1.50:9000`.

### O que e docker-compose?

Uma ferramenta para criar e rodar varios containers do docker de uma vez de forma mais facil. Em um arquivo .yaml voce define todos os parametros dos containers tornando muito facil atualizar todos de uma vez, restaurar, gerenciar.

### Instalando docker-compose

**Instalar as dependencias**
```
sudo apt-get install -y libffi-dev libssl-dev
sudo apt-get install -y python3 python3-pip
sudo apt-get remove python-configparser
```

**Instalar docker compose**
```
sudo pip3 install docker-compose
```

Docker: [Documentacao oficial docker](https://docs.docker.com/)
Compose: [Documentacao oficial docker-compose](https://docs.docker.com/compose/)
