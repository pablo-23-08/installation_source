# INSTALLATION DES PAQUETS mysql, apache ET php  À PARTIR DE CODES SOURCES

    • Téléchargeons les codes sources des paquets dans les liens qui suivent : 
    1. mysql :   http://www.mysql.com/downloads/msql
    2. apache : https://httpd.apache.org/download.cgi#apache2.4
    3. php: https://www.php.net/downloads.php


     #• Pour l’installation de  mysql
Désarchivons et décompressons mysql-8.0.36.tar.gz que nous avons téléchargé avec la commande qui suit :
				~$  tar -zxvf mysql-8.0.36.tar.gz
			 
Entrons dans le dossier mysql-8.0.36 par la commande : 
				~$ cd  mysql-8.0.36
		Dans ce dossier il y a un fichier nommé INSTALL qui nous informe comment se fait l’installation. Après avoir lu le fichier INSTALL, nous savons maintenant que pour faire l’installation .

    1. Faisons ~/mysql-8.0.36$ mkdir build pour créer un répertoire du nom build puis entrons dans ce repértoire par ~/mysql-8.0.36$ cd build
 
    2. Exécutons ensuite la commande ~/mysql-8.0.36/build$ sudo cmake ..
	Il y a une longue erreur comme 
Cmake Error at cmake/boost.cmake:108 (MESSAGE) :
	You can download it with -DOWNLOAD_BOOST=1 -DWITH_BOOST=<directory>
	…
See also  «/home/usr/mysql-8.0.36/build/CmakeFiles/CmakeOutput.log»
See also  «/home/usr/mysql-8.0.36/build/CmakeFiles/CmakeError.log»
				Pour résoudre cette erreur nous devons télécharger boost_1_77_0.tar.bz2 et l’installer. Procédons alors comme-ci :
    • Pour désarchiver et décompresser : ~$  tar -jxvf  boost_1_77_0.tar.bz2
    • Entrer dans le dossier : ~$ cd  boost_1_77_0
    • ~/boost_1_77_0$ ./bootstrap.sh
    • ~/boost_1_77_0$ sudo ./b2
    • ~/boost_1_77_0$ sudo ./b2 install
On retape alors ~/mysql-8.0.36/build$ sudo cmake .. , cette fois-ci il n’y a plus d’erreur. 

    3. On exécute maintenant ~/mysql-8.0.36/build$ sudo make 
    4. Et enfin on termine avec la commande ~/mysql-8.0.36/build$ sudo make install

Pour savoir que mysql s’est installé on regarde quelle version est installé par la commande :
	$ /usr/local/mysql/bin/mysql --version


    #• Pour l’installation de  apache
Désarchivons et décompressons httpd-2.4.59.tar.bz2 que nous avons téléchargé avec la commande qui suit :
				~$  tar -jxvf httpd-2.4.59.tar.bz2

Entrons dans le dossier mysql-8.0.36 par la commande : 
				~$ cd httpd-2.4.59
		Dans ce répertoire s’y trouve un fichier nommé INSTALL qui nous explique comment se fait l’installation. Après avoir lu ce fichier, nous procédons à ce qui est indiqué.

    1. On exécute la commande : ~/httpd-2.4.59$ ./configure
		Une erreur s’affiche : 
configure : error: APR not found.  Please read the documentation
		Pour corriger cette erreur on exécute les commandes suivantes :
    • Pour mettre à jour le serveur :
				$ sudo apt-get update
    • Pour installer apr et apr-util :
				$ sudo apt-get install libapr1-dev libapr-util1-dev
		
	     On relance ensuite ~/httpd-2.4.59$ ./configure
		Une autre erreur s’affiche :
configure : error : pcre(2)-config for lib pcre not found. PCRE is required and available from http://pcre.org/
		Pour y remédier à cette autre erreur, on exécute la commande suivante :
			$ sudo apt-get install libpcre3-dev
		
	      On relance encore ~/httpd-2.4.59$ ./configure , cette fois-ci il n’y a plus d’erreur.

    2. On lance la commande : ~/httpd-2.4.59$ sudo make
    3. Et on termine avec la commande : ~/httpd-2.4.59$ sudo make install
Pour savoir que apache s’est installé on regarde s’il marche avec la commande :
	$ sudo /usr/local/apache2//bin/apachectl start


    #• Pour l’installation de  php
On désarchive et décompresse php-8.1.28.tar.bz2 avec la commande qui suit :
				~$  tar -jxvf php-8.1.28.tar.bz2

Entrons dans le dossier mysql-8.0.36 par la commande : 
				~$ cd  php-8.1.28

Exécutons ensuite les commandes suivantes :

    1. ~/php-8.1.28$ ./configure
	
	Il y a une erreur : 
configure : error: xml2-config not found. Please check your libxml2 installation
	Pour corriger cette erreur on installe xml2 avec :
		$ sudo apt-get install libxml2-dev
	On retape après $ ./configure , mais une autre erreur s’affiche :
configure : error : Package requirments (sqlite3 > 3.7.4) were not met : No package ‘sqlite3’ found
	Pour corriger cette autre erreur on doit installer sqlite3 par la commande :
		$ sudo apt-get install libsqlite3-dev
	On relance la commande $ ./configure , cette fois-ci il n’y a plus d’erreur.
	
    2. On lance la commande : ~/php-8.1.28$ sudo make
    3. Et on termine avec la commande : ~/php-8.1.28$ sudo make install
Pour savoir que php s’est installé on regarde sa version avec la commande :
	$ php -v
		
