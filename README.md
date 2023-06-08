# Sql-injection
Execution de la vulnérabilité d'injection SQL sur Service Provider Management System v1.0

#### Exploit Title: Service Provider Management System v1.0 - SQL Injection
#### Date: 2023-05-23
#### Exploit Author: Ashik Kunjumon
#### Vendor Homepage: https://www.sourcecodester.com/users/lewa
#### Software Link: https://www.sourcecodester.com/php/16501/service-provider-management-system-using-php-and-mysql-source-code-free-download.html
#### Version: 1.0
#### Testé sur: Linux

###1. Description :

Le système de gestion des fournisseurs de services v1.0 permet une injection SQL via le paramètre ID
dans #####/php-spms/?page=services/view&id=2
L'exploitation de ce problème pourrait permettre à un attaquant de compromettre l'application
compromettre l'application, d'accéder à des données ou de les modifier,
ou d'exploiter les dernières vulnérabilités de la base de données sous-jacente.

####Point final : /php-spms/?page=services/view&id=2

####Paramètre vulnérable : id (GET)

###2. Preuve de concept :
###Etape 1- Installation de l’application web vulnérable
Pour cette étape nous essayerons de déployer l’application sur xampp.


On cré une base de donnée portant le nom de #####spms_db
![Capture d’écran du 2023-06-07 12-14-55](https://github.com/rozzario/Sql-injection/assets/36795507/29b5a31f-3d3c-48f8-937c-ca2cf1810f6d)

Puis on importe le contenu de la base de donnée:
![Capture d’écran du 2023-06-07 12-16-15](https://github.com/rozzario/Sql-injection/assets/36795507/65edaaf6-f0e1-4148-a100-bb11a4d76f4c)

Une fois que c’est fait, on déploie l’application en copiant le dossier du site web dans le répertoire htdocs de xampp. On obtient donc ceci:
![Capture d’écran du 2023-06-07 12-18-00](https://github.com/rozzario/Sql-injection/assets/36795507/1391e28f-96d0-413d-849c-15c078e52d51)

###Étape 2 - En visitant l'url :
http://localhost/php-spms/?page=services/view&id=2, il suffit d'ajouter un guillemet simple pour
vérifier l'injection SQL.
![Capture d’écran du 2023-06-07 12-18-53](https://github.com/rozzario/Sql-injection/assets/36795507/7cd464c3-0634-4e6d-8c8b-6a0c8880c245)
![Capture d’écran du 2023-06-07 12-19-24](https://github.com/rozzario/Sql-injection/assets/36795507/62b380b6-18ea-444c-84f4-a921a93210ee)

###Etape 3 - Exécuter sqlmap -u " http://localhost/php-spms/?page=services/view&id=2"
-p id --dbms=mysql



