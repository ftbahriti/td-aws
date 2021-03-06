# TD AWS

## Présention
Le but du TD est d'apprendre les services de base d'AWS comme EC2, RDS

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


# Pour installer PHP7.2
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

sudo a2dismod php7.1
sudo a2enmod php7.2

sudo service apache2 restart
```


# Créé un sous domaine

- A l'aide du service AWS route 53, créé un sous domaine pointant vers l'adresse IP Publique de votre instance

# Configuration du VHOST sur l'instance

- `sudo vi /etc/hosts`   OU `sudo nano /etc/hosts `

Ajouter la ligne de configuration de votre domaine comme suit:

`127.0.0.1 gary-aka-le-prof.ipssi-squad.fr`


## Création d'une base de donnée dans le cluster RDS aurora

- Téléchargez Mysql Workbench => https://www.mysql.com/fr/products/workbench/
- Connectez vous au cluster de donnée aurora via workbench (info envoyé sur slack)
- Créez vous un compte utilisateur
- Créez vous une base de donnée (et mettez les identifiants dans un coin pour demain)


## Création d'un bucket AWS S3

- Allez dans le panneau de controle AWS S3 
- Creez vous un bucket à votre nom 



## Projet sur 1 jour et demi 
### Presentation
Le projet comptera pour la note
L'idée du projet est de réaliser un service sur AWS.
Fin de la session de projet vendredi midi.
Vendredi après midi, chaque équipe présentera son projet devant le reste de la classe.

- Critère de notation
  - Utiliser des services que l'on n'a pas vu pendant les cours de base cad ec2, s3, rds, route53
  - Utiliser au moins 2 ou 3 services
  - Utiliser le SDK dans le language de programmation de votre choix => https://aws.amazon.com/fr/tools/#sdk
  - Plus il y a de personnes dans le groupe, plus le projet devra être lourd

- Critère qui ne compterons pas 
  - La qualité du code (seulement pour cette fois)
  
  
### Rapport

- Créer un projet sur github pour votre groupe de projet
- Envoyez moi l'url de votre projet github
- Mettez dans le README.md, les noms des participants au projet, la description du projet, les services AWS qui seront utilisés et pourquoi.
- Pensez à push régulièrement votre travail sur github 

/!\ Ne pas commit les clés publiques!

### Exemple d'idée de projet
- Utilisation de l'api rekognition pour faire de la reconnaissance facial
- Utilisation de comprehend pour faire de l'analyse de texte
- Utilisation de aws lambda pour gérer une de redirection email
- Utilisation de aws SES pour faire un outil d'envoie d'email de mass
- Utilisation de Kinesis pour faire un site de streaming video ( comme netflix)
- Utilisation de Cloudfront pour la création d'un CDN
- Utilisation de AWS Machine Learning pour faire de la prédiction de donnée
- Utilisation de AWS Poly pour transformer du text en voix
- Utilisation d'AWS beanstalk pour créé un groupe instance EC2 avec load balancer et autoscaling groupe
- 


### FAQ

- Je suis sous windows et je n'arrive pas à me connecter à mon serveur
  => installer ubuntu pour windows via le windows store

  
### Liens vers les projets
https://github.com/macrorobot/aws-in-translation
https://github.com/sturquier/aws-project
https://github.com/Matt75/aws-ses
https://github.com/Taghoria/aws
https://github.com/RayaneYagoubi/rss-feeds-parser
https://github.com/ehalifa/squadproj
https://github.com/Username34/Animadex


### Bonus (rien à voir avec le cours) 

Pour ceux qui veulent faire des APIs REST easy => https://github.com/zfcampus/zf-apigility-skeleton







