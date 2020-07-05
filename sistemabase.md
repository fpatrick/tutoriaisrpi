[CLIQUE AQUI](https://fpatrick.github.io/tutoriaisrpi/) PARA VOLTAR AO INICIO.

# Ajustes apos instalacao
Guia de procedimentos que podem ser uteis apos instalacao limpa do sistema. (Testado no Raspbian OS lite).

### Desativar swap
Extremamente recomendado, especialmente para quem usa cartao SD. Por padrao o raspbian os vem com 100 MB de memoria swap ativado. Caso voce esteja utilizando cartao SD, SSD ou tenha um raspberry com no minimo 4GB de ram, e recomendado que o swap deja desativado. Por que? Com 4 GB de ram voce difilmente ira precisar do swap, caso esteja utilizando SD ou SSD e ainda pior, pois ele encurta a vida util refazendo escritas. 
Para desativar execute o codigo: 
```
sudo systemctl disable dphys-swapfile.service
```
Reinicie e execute o seguinte codigo para confirmar que swap agora e 0:
```
free -m
```
### Fazer montagem do HD Externo
Recomendo seguir a documentacao oficial que e muito detalhada caso seu hd esteja formatado em ext4, ntfs, etc. Nao esqueca de fazer a parte para montar automaticamente apos reboot. https://www.raspberrypi.org/documentation/configuration/external-storage.md

### Montar SMB
Instala o SMB
```
sudo apt-get install samba samba-common-bin
```
Cria a pasta que deseja compartilhar no SMB, exemplo:
```
mkdir /compartilhado
```
Edita o arquivo de configuracao do smb para adicionar a pasta que criamos:
```
sudo nano /etc/samba/smb.conf
```
Aperta a tecla page down ate descer ao final do arquivo e adicione isso (editando a primeira linha com o nome que quiser e a segunda com o caminho da pasta que quer compartilhar):
```
[raspsmb]
path = /compartilhado
writeable=Yes
create mask=0777
directory mask=0777
public=no
```
Aperte as teclas Ctrl + X, depois y depois enter para salvar a configuracao.
Crie um usuario para acesso do smb com o nome que desejar (no exemplo usado, usuario pi):
```
sudo smbpasswd -a pi
```
Por fim reinicie o servico:
```
sudo systemctl restart smbd
```

mount usb


fazer smb


desativar memoria swap
sudo systemctl disable dphys-swapfile.service
free -m
padrao 100 mb
