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
Etape 1- Installation de l’application web vulnérable
Pour cette étape nous essayerons de déployer l’application sur xampp.


On cré une base de donnée portant le nom de #####spms_db

