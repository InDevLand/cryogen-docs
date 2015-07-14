{:title "VPS avec nginx"
 :layout :page
 :page-index 7
 :section "D&eacute;ploiement"}

Un serveur priv&eacute; virtuel (VPS), tel que ceux disponibles chez [DigitalOcean](https://www.digitalocean.com/), est une bonne mani&egrave;re d&apos;h&eacute;berger un site au contenu statique pour environ 5$ par mois. Voici une proc&eacute;dure rapide sur comment rendre votre contenu disponible avec [Nginx](http://wiki.nginx.org/) s&apos;ex&eacute;cutant dans un VPS sous Ubuntu.



## Configurer nginx

La premi&egrave;re chose &agrave; faire est d&apos;installer nginx si ce n&apos;est d&eacute;j&agrave; fait.

```
$ sudo apt-get install nginx
```

Ensuite, cr&eacute;ez un r&eacute;pertoire pour le contenu de votre site et rendez le public. Pour ce guide, supposons que nous utilisons un utilisateur appel&eacute; `deploy` qui dispose des droits sudo.

```
$ mkdir ~/site
$ chmod 755 ~/site
```

Maintenenat, faite une sauvegarde de la configuration par d&eacute;faut dans /etc/nginx/sites-available/default et remplacez le contenu avec un des choix suivants:

### Configuration d'un site sans blog-prefix

```
server {
 listen 80;

 root /home/deploy/site;
 index index.html index.htm;

 server_name VOTREDOMAINE.COM www.VOTREDOMAINE.COM;

 access_log /var/log/nginx/access.log;
 error_log /var/log/nginx/error.log;

 location / {
   default_type "text/html";
   alias /home/deploy/site/;
   try_files $uri.html $uri $uri/ =404;
   error_page    404 = /404.html;
 }
}
```

Remplacez simplement `VOTREDOMAINE.COM` par votre domaine pour le site dans la configuration et v&eacute;rifiez que le contenu statique est disponible dnas `/home/deploy/site/`. Pour finir, placez votre page d&apos;erreur personalis&eacute;e dans le fichier `/home/deploy/site/404.html`.

### Configuration d'un site utilisant un blog-prefix

Si vous avez d&eacute;fini un `blog-prefix` dans le fichier de configuration de Cryogen, vous devez en tenir compte dans la configuration de nginx.

```
server{
 listen 80;

 root /home/deploy/site;
 index index.html index.htm;
 error_page    404 = /404.html;

 server_name VOTREDOMAINE.COM www.VOTREDOMAINE.COM;

 access_log /var/log/nginx/access.log;
 error_log /var/log/nginx/error.log;

 location / {
   default_type "text/html";
   try_files $uri.html $uri $uri/ =404;
 }

 location /BLOG-PREFIX/ {
   alias /home/deploy/site/BLOG-PREFIX/;
 }
}
```

Repmplacez simplement `VOTREDOMAINE.COM` par votre domaine pour le site dans la configuration et v&eacute;rifiez que le conentu statique est disponible dans `/home/deploy/site/BLOG-PREFIX/`. Pour finir, placez votre page d&apos;erreur personalis&eacute;e dans le fichier `/home/deploy/site/404.html`.

Une fois le fichier de configuration de nginx adapt&eacute;, red&eacute;marrez nginx.

```
$ sudo service nginx restart
```

## D&eacute;ployer votre site

Quand votre serveur est pr&ecirc;t &agrave; h&eacute;berger votre site, vous devez t&eacute;l&eacute;charger le contenu vers votre serveur. Vous pouvez le faire en utilisant un client FTP comme [FileZilla](https://filezilla-project.org/) ou en utilisant la commande `scp` depuis un terminal.

Si vous souhaitez cnager ou ajouter plus de contenu &agrave; votre site apr&egrave;s son d&eacute;ploiement, retansferez simplement le contenu g&eacute;n&eacute;r&eacute; par Cryogen.
