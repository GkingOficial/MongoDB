# Manual de instalação do MongoDB Compass

## Passos iniciais

Faremos a instalação pelo terminal.

O primeiro passo é baixar o instalador (.deb) do MongoDB Compass

```bash
wget https://downloads.mongodb.com/compass/mongodb-compass_1.32.2_amd64.deb
```

Em seguida, extraímos e instalamos o arquivo.

```bash
sudo dpkg -i mongodb-compass_1.32.2_amd64.deb
```

Agora é só executar o MongoDB Compass

```bash
mongodb-compass
```