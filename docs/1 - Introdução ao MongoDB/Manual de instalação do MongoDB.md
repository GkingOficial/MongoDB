# Manual de instalação do MongoDB

## Passos iniciais

O pré-requisito de instalação de banco de dados é a preparação do servidor. É necessário criar um novo usuário sudo (não root)
que tenha os privilégios ajustados no firewall.

O primeiro passo é atualizar o gerenciador de pacotes

```bash
sudo apt update
```

E instalar algumas dependências.

```bash
sudo apt install dirmngr gnupg apt-transport-https ca-certificates software-properties-common
```

Em seguida, baixe a chave do repositório.

```bash
wget -qO - https://www.mongodb.org/static/pgp/server-4.4.asc | sudo apt-key add -
```

Se tudo correr bem, o terminal retornará uma mensagem de confirmação.

Agora, será preciso verificar qual é a versão do seu sistema usando o comando abaixo:

```bash
lsb_release -crs
```

O passo seguinte dependerá de qual é a versão do seu sistema.

- Se seu sistema é um Ubuntu 20.04 ou derivado
    
    ```bash
    echo "deb [ arch=amd64,arm64 ] https://repo.mongodb.org/apt/ubuntu focal/mongodb-org/4.4 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-4.4.list
    ```
    
- Se seu sistema é um Ubuntu 18.04 ou derivado
    
    ```bash
    echo "deb [ arch=amd64,arm64 ] https://repo.mongodb.org/apt/ubuntu bionic/mongodb-org/4.4 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-4.4.list
    ```
    
- Se seu sistema é um Ubuntu 16.04 ou derivado
    
    ```bash
    echo "deb [ arch=amd64,arm64 ] https://repo.mongodb.org/apt/ubuntu xenial/mongodb-org/4.4 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-4.4.list
    ```
    

Atualize novamente o gerenciador de pacotes.

```bash
sudo apt update
```

Agora podemos instalar o programa.

```bash
sudo apt install mongodb-org
```

*Por padrão, o MongoDB é executado sob a conta de usuário mongodb. Se alterarmos os usuários, devemos também alterar a permissão para os diretórios de dados e registros, para atribuir acesso a esses diretórios*

Agora podemos iniciar e verificar o processo mongod executando os seguintes comandos:

```bash
sudo systemctl start mongod
```

```bash
sudo systemctl status mongod
```

```bash
sudo service mongod start
```

```bash
sudo service mongod status
```

Pronto! Se tudo estiver correto, podemos iniciar o mongodb que estará sendo executado em nosso host local usando a porta padrão 27017:

```bash
mongo
```