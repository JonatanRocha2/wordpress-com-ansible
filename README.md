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


### WordPress Precisa do PHP!

![WordPress Theme Required PHP Version](https://img.shields.io/wordpress/theme/required-php/%3E=7?style=for-the-badge)

## Criando um ambiente de desenvolvimento

1. Escolha a melhor forma de provisionar seu ambiente de desenvolvimento: Docker ou Vagrant.

- Caso queira criar containers usando docker, acesse o diretorio [docker](/docker/) e use o [Dockerfile](/docker/Dockerfile)

- Caso queira usar o [Vagrant](https://www.vagrantup.com/downloads), você também precisará instalar o [Virtual Box](https://www.virtualbox.org/wiki/Downloads)