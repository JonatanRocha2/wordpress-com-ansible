# Como automatizar a criação de um servidor Wordpress com Ansible

### Projeto realizado para estudar ansible. Para maior facilidade, as imagens podem ser baixadas já configuradas diretamente do [Docker Hub](https://hub.docker.com/search?q=).

- [Apache](https://hub.docker.com/_/httpd)
- [PHP](https://hub.docker.com/_/php)
- [MariaDB](https://hub.docker.com/_/mariadb)
- [Wordpress](https://hub.docker.com/_/wordpress)

### Tecnologias usadas


<a href="https://docs.ansible.com/ansible/latest/index.html" alt="Ansible Documentation">
<img src="https://img.shields.io/badge/ansible-%231A1918.svg?style=for-the-badge&logo=ansible&logoColor=white"/>
</a>

<a href="https://docs.docker.com/get-started/overview/" alt="Docker Documentation">
<img src="https://img.shields.io/badge/docker-%230db7ed.svg?style=for-the-badge&logo=docker&logoColor=white"/>
</a>

<a href="https://mariadb.com/kb/en/documentation/" alt="MariaDB Documentation">
<img src="https://img.shields.io/badge/MariaDB-003545?style=for-the-badge&logo=mariadb&logoColor=white"/>
</a>

<a href="https://developer.wordpress.com/docs/" alt="Wordpress Documentation">
<img src="https://img.shields.io/badge/Wordpress-21759B?style=for-the-badge&logo=wordpress&logoColor=white"/>
</a>


## Criando o ambiente de desenvolvimento

1. Instale o docker e o docker-compose 

- [Docker](https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-on-ubuntu-22-04)

- [Docker Compose](https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-compose-on-ubuntu-22-04)

```
docker-compose up -d
```

2. Execute o comando para configurar os alvos definidos no arquivo "hosts"

```
ansible-playbook provisioning.yml -i hosts 
```

3. Caso seja necessário, altere a permissao de acesso da aplicacao ao banco de dados

```
MariaDB [(none)]> GRANT ALL ON database_name.* to 'database_username'@'database_ip' IDENTIFIED BY 'database_password';
MariaDB [(none)]> FLUSH PRIVILEGES;
MariaDB [(none)]> SELECT host FROM mysql.user WHERE user = "database_username";
```