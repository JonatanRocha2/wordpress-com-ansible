# Como automatizar a criação de um servidor Wordpress

### Tecnologias usadas


<a href="https://docs.ansible.com/ansible/latest/index.html" alt="Ansible Documentation">
<img src="https://img.shields.io/badge/ansible-%231A1918.svg?style=for-the-badge&logo=ansible&logoColor=white"/>
</a>

<a href="https://docs.docker.com/get-started/overview/" alt="Docker Documentation">
<img src="https://img.shields.io/badge/docker-%230db7ed.svg?style=for-the-badge&logo=docker&logoColor=white"/>
</a>

<a href="https://www.vagrantup.com/docs" alt="Vagrant Documentation">
<img src="https://img.shields.io/badge/vagrant-%231563FF.svg?style=for-the-badge&logo=vagrant&logoColor=white"/>
</a>

## Criando um ambiente de desenvolvimento

1. Escolha a melhor forma de provisionar seu ambiente de desenvolvimento: Docker ou Vagrant.

2. Comando para executar o ansible no host
```
ansible-playbook provisioning.yml -i hosts 
```

- ansible-playbook: comando que executa um manual de instruções informados por um arquivo .yml
- -i : arquivo de origem com os alvos que serão modificados

3. Corrigindo permissao de acesso da aplicacao ao banco de dados

```
MariaDB [(none)]> GRANT ALL ON database_name.* to 'database_username'@'10.24.96.5' IDENTIFIED BY 'database_password';
MariaDB [(none)]> FLUSH PRIVILEGES;
MariaDB [(none)]> SELECT host FROM mysql.user WHERE user = "database_username";
```