# Docker e docker compose

Docker: [Documentacao oficial docker](https://docs.docker.com/)
Compose: [Documentacao oficial docker-compose](https://docs.docker.com/compose/)

### O que e docker
Todos conhecemos a ideia de virtualizar um sistema operacional atraves do virtualbox ou outro servico semelhante. Basicamente o docker e a mesma coisa, mas virtualizando aplicativos ao inves de sistemas operacionais.

### Por que usar?
1. Sem dependencias. Os servicos podem precisar de bibliotecas ou terem dependencias para funcionar, assim como no windows as vezes um programa pede pra instalar o java para abrir. No linux isso e muito mais complexo, onde um servico pode precisar do python 2.6 e outro do python 2.5, com tantas versoes conflitando nem tudo pode ser tao facil manter. Dentro do container ja vem todas bibliotecas e dependencias que o servico precisa para rodar perfeitamente.

2. Instalacao. Instalar um servico pelo docker e tao simples quanto baixar um arquivo. Nada da complexidade do linux de compilar da fonte ou procurar pacotes prontos.

3. Facilidade de gerenciar. Voce pode pausar, excluir, restaurar muito facilmente qualquer servico dentro de containers de docker.

### Instalando docker e compose

**Instalar**
```
curl -sSL https://get.docker.com | sh
```

**(Opcional) Dar permissao ao padrao, para usar docker sem sudo**
```
sudo usermod -aG docker pi
```

**Verficar se funciona**
```
docker run hello-world
```

###Instalando docker-compose

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
