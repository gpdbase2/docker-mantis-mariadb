# docker-mantis-mariadb

# 1. Preparação do ambiente Mantis

Será necessário baixar os seguintes softwares para iniciar o projeto:

**1.1 Preparação Mantis + MariaDB**

 1. [Docker Toolbox](https://docs.docker.com/toolbox/toolbox_install_windows/)
 2. Criar uma pasta "mantis" no diretório raiz (ex: C:\mantis)
 3. Executar o software *Docker Quickstart Terminal*
 4. Acessar o diretório através do terminal aberto no passo anterior
 5. Incluir no diretório o arquivo docker-compose.yml
 6. Executar o comando> `docker-compose.exe up -d`
 7. Após o processamento, para validar execute o comando `docker ps -a` e os contêineres estarão disponíveis.
 

**1.2 Configuração máquina remota**

 1. Com o tópico 1.1 já realizado, executar no *Docker Quickstart Terminal*, o comando `docker-machine ip` e coletar a informação
 2. Abrir o software VirtualBox
3. Encontrar a imagem referente ao docker
4. Acessar "Configurações"
5. Acessar "Redes"
6. Acessar "Avançado"
7. Acessar "Redirecionamento de Portas"
8. A configuração para funcionar no  docker  toolbox deverá estar dessa maneira:
![enter image description here](https://i.imgur.com/nUKTsr2.png)
9.  Incluir linha conforme nome "docker"
10.  Protocolo: TCP
11.  Endereço de Hospedeiro: 127.0.0.1
12.  Porta de Hospedeiro: 80
13.  IP Convidado preenchido com o valor recebido do  docker  (docker-machine ip default): 192.168.99.100
14.  Porta do convidado: 80

O ambiente Mantis deverá estar disponível em: http://192.168.99.100:8989

**1.3 Configuração inicial Mantis**

Para o primeiro acesso ao Mantis, será necessário configurar o banco de dados conforme tabela abaixo:

| Variável | Valor |
|------|--------|
| Type of Database | MySQL Improved |
| Hostname (for Database Server) | mantis_db_1 |
| Username (for Database) | mantisbt |
| Password (for Database) | mantisbt |
| Database name (for Database) | bugtracker |
| Admin Username (to create Database if required) | root |
| Admin Password (to create Database if required) | root |

Após preencher, clicar em **Login/Continue** e aguardar o processamento (demora cerca de 10 minutos).
O primeiro acesso deverá ser feito utilizando as credenciais *administrator/root*. Redefinir a senha para o valor *administrator*.

**1.4 Configuração inicial MariaDB**

1. Abrir o software VirtualBox
2. Encontrar a imagem referente ao docker
3. Acessar "Configurações"
4. Acessar "Redes"
5. Acessar "Avançado"
6. Acessar "Redirecionamento de Portas"
7. A configuração para funcionar no  docker toolbox deverá estar dessa maneira:
![enter image description here](https://i.imgur.com/09lJxzV.png)
8.  Incluir linha conforme nome "docker"
9.  Protocolo: TCP
10.  Endereço de Hospedeiro: 127.0.0.1
11.  Porta de Hospedeiro: 3306
12.  IP Convidado preenchido com o valor recebido do docker  (docker-machine ip default): 192.168.99.100
13.  Porta do convidado: 3306

Para acessar o banco de dados, utilize algum SGBD MySQL (exemplo: Heidi SQL) com as credenciais listadas acima.
