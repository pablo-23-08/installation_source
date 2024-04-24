# source-code_installation
Voici une conversion en HTML du texte que vous avez fourni :

```html
<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Installation des paquets MySQL, Apache et PHP à partir de codes sources</title>
</head>
<body>
    <h1>INSTALLATION DES PAQUETS MYSQL, APACHE ET PHP À PARTIR DE CODES SOURCES</h1>

    <h2>Téléchargement des codes sources</h2>
    <ol>
        <li><a href="http://www.mysql.com/downloads/msql">mysql</a></li>
        <li><a href="https://httpd.apache.org/download.cgi#apache2.4">apache</a></li>
        <li><a href="https://www.php.net/downloads.php">php</a></li>
    </ol>

    <h2>Installation de MySQL</h2>
    <p>Téléchargez le fichier mysql-8.0.36.tar.gz et exécutez les commandes suivantes :</p>
    <pre>
        <code>~$ tar -zxvf mysql-8.0.36.tar.gz</code>
        <code>~$ cd mysql-8.0.36</code>
        <code>~$ mkdir build</code>
        <code>~$ cd build</code>
        <code>~$ sudo cmake ..</code>
        <code>~$ sudo make</code>
        <code>~$ sudo make install</code>
    </pre>
    <p>Vérifiez la version de MySQL avec :</p>
    <pre><code>$ /usr/local/mysql/bin/mysql --version</code></pre>

    <h2>Installation d'Apache</h2>
    <p>Téléchargez le fichier httpd-2.4.59.tar.bz2 et exécutez les commandes suivantes :</p>
    <pre>
        <code>~$ tar -jxvf httpd-2.4.59.tar.bz2</code>
        <code>~$ cd httpd-2.4.59</code>
        <code>~$ ./configure</code>
        <code>$ sudo apt-get update</code>
        <code>$ sudo apt-get install libapr1-dev libapr-util1-dev</code>
        <code>$ sudo apt-get install libpcre3-dev</code>
        <code>~$ sudo make</code>
        <code>~$ sudo make install</code>
    </pre>
    <p>Vérifiez si Apache fonctionne :</p>
    <pre><code>$ sudo /usr/local/apache2/bin/apachectl start</code></pre>

    <h2>Installation de PHP</h2>
    <p>Téléchargez le fichier php-8.1.28.tar.bz2 et exécutez les commandes suivantes :</p>
    <pre>
        <code>~$ tar -jxvf php-8.1.28.tar.bz2</code>
        <code>~$ cd php-8.1.28</code>
        <code>~$ ./configure</code>
        <code>$ sudo apt-get install libxml2-dev</code>
        <code>$ sudo apt-get install libsqlite3-dev</code>
        <code>~$ sudo make</code>
        <code>~$ sudo make install</code>
    </pre>
    <p>Vérifiez la version de PHP avec :</p>
    <pre><code>$ php -v</code></pre>
</body>
</html>
```

Cette version HTML reproduit le contenu original dans une mise en forme HTML standard.
