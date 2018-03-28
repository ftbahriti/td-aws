# TD AWS

  - url du projet: https://www.github.com/garygitton/td-aws

- Se creer un compte AWS 

aws.amazon.com

- Pour ceux qui veulent que je leur créé un compte faite moi une demande sur ipssi@garygitton.fr

- Installer le CLI AWS sur https://docs.aws.amazon.com/cli/latest/userguide/installing.html

## EC2 

- Création d'une instance ec2 t2.micro
- Configuration du groupe de sécurité, 
  - Fermer les ports autres que 22, 80, 443 et 3000 en inbound
  
- se connecter en SSH
- Installer le CMS grav


# Pour installer apache 
## Installation
sudo apt-get install -y apache2
sudo apt-get install -y apache2-utils 

### Configuration
sudo a2enmod rewrite
sudo a2enmod headers

### Add my username to wwww-data group
sudo usermod -a -G www-data "$USER"

### Change owner of /var/www folder to “$USER”:www-data 
sudo chown -R "$USER":www-data /var/www


# Pour installer PHP7.1
sudo add-apt-repository ppa:ondrej/php
sudo apt-get install -y language-pack-en-base
sudo apt-get update
sudo apt-get upgrade

sudo apt-get -y install php7.1
sudo apt-get -y install php7.1-mysql 
sudo apt-get -y install php7.1-curl 
sudo apt-get -y install php7.1-intl 
sudo apt-get -y install php7.1-mcrypt 
sudo apt-get -y install php7.1-xml
sudo apt-get -y install php7.1-mbstring
sudo apt-get -y install php7.1-pdo
sudo apt-get -y install php7.1-common
sudo apt-get -y install php7.1-zip
sudo apt-get -y install php7.1-cli

sudo service apache2 restart


# Créé un sous domaine

- A l'aide du service AWS route 53, créé un sous domaine pointant vers l'adresse IP Publique de votre instance

# Configuration du VHOST sur l'instance

- 




