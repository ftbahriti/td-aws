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


# Installer les packages basic de l'instance
```bash 
sudo apt-get update
sudo apt-get upgrade -y

sudo apt-get install -y curl
sudo apt-get install -y apt-transport-https
sudo apt-get install -y ca-certificates
sudo apt-get install -y software-properties-common
sudo apt-get install -y git

```

# Pour installer apache 
## Installation
```
sudo apt-get install -y apache2
sudo apt-get install -y apache2-utils 
```

### Configuration
```
sudo a2enmod rewrite
sudo a2enmod headers
```

### Add my username to wwww-data group
`sudo usermod -a -G www-data "$USER"`

### Change owner of /var/www folder to “$USER”:www-data 
`sudo chown -R "$USER":www-data /var/www`


# Pour installer PHP7.1
```
sudo add-apt-repository ppa:ondrej/php
sudo apt-get install -y language-pack-en-base
sudo apt-get update
sudo apt-get upgrade

sudo apt-get -y install php7.2
sudo apt-get -y install php7.2-mysql 
sudo apt-get -y install php7.2-curl 
sudo apt-get -y install php7.2-intl 
sudo apt-get -y install php7.2-mcrypt 
sudo apt-get -y install php7.2-xml
sudo apt-get -y install php7.2-mbstring
sudo apt-get -y install php7.2-pdo
sudo apt-get -y install php7.2-common
sudo apt-get -y install php7.2-zip
sudo apt-get -y install php7.2-cli

sudo service apache2 restart
```


# Créé un sous domaine

- A l'aide du service AWS route 53, créé un sous domaine pointant vers l'adresse IP Publique de votre instance

# Configuration du VHOST sur l'instance

- `sudo vi /etc/hosts`   OU `sudo nano /etc/hosts `

Ajouter la ligne de configuration de votre domaine comme suit:

`127.0.0.1 gary-aka-le-prof.ipssi-squad.fr`









