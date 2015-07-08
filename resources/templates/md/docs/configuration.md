{:title "Configuration"
 :layout :post
 :page-index 3
 :section "D&eacute;marrer"}

Cryog&egrave;ne offre des options de configuration flexibles. Le fichier de configuration de votre site se trouve dans le r&eacute;pertoire `templates/config.edn` et contient les valeurs suivantes:

```
{:site-title       "My Awesome Blog"
 :author           "Bob Bobbert"
 :description      "This blog is awesome"
 :site-url         "http://blogawesome.com/"
 :post-root        "posts"
 :tag-root         "tags"
 :page-root        "pages"
 :blog-prefix      "/blog"
 :recent-posts     5
 :post-date-format "yyyy-MM-dd"
 :rss-name         "feed.xml"
 :rss-filters      ["cryogen"]
 :sass-src         nil
 :sass-dest        nil
 :resources        ["css" "js" "img"]
 :keep-files       [".git"]
 :disqus?          false
 :disqus-shortname ""
 :ignored-files    [#"\.#.*" #".*\.swp$"]}
```

## Options

<table class="table table-bordered">
  <thead>
    <tr>
      <th>Mot-cl&eacute;</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>`site-title`</td>
      <td>Le nom de votre site</td>
    </tr>
    <tr>
      <td>`author`</td>
      <td>Mettez votre nom ici!</td>
    </tr>
    <tr>
      <td>`description`</td>
      <td>Un texte de pr&eacute;sentation d&eacute;crivant votre site</td>
      </tr>
      <tr>
        <td>`site-url`</td>
        <td>L&apos;url de base de votre site. Cette valeur est utilis&eacute;e pour g&eacute;n&eacute;rer la carte du site et le flux RSS.</td>
      </tr>
      <tr>
        <td>`post-root`</td>
        <td>Le r&eacute;pertoire dans lequel le compilateur cherche les articles. Cette valeur est ins&eacute;r&eacute;e devant l&apos;uri de tous les articles. Elle doit &ecirc;tre fournie.</td>
      </tr>
      <tr>
        <td>`tag-root`</td>
        <td>Cette valeur est ins&eacute;r&eacute;e devant l&apos;uri des pages de tag. Elle doit &ecirc;tre fournie.</td>
      </tr>
      <tr>
        <td>`page-root`</td>
        <td>Le r&eacute;pertoire dans lequel le compilateur cherche les pages. Cette valeur est ins&eacute;r&eacute;e devant l&apos;uri de toutes les pages. Elle doit &ecirc;tre fournie.</td>
      </tr>
      <tr>
        <td>`blog-prefix`</td>
        <td>Cette valeur est ins&eacute;r&eacute;e devant l&apos;uri des articles. Elle doit &ecirc;tre fournie.</td>
      </tr>
      <tr>
        <td>`recent-posts`</td>
        <td>Le nombre maximum d&apos;articles r&eacute;cents &agrave; montre dans la barre lat&eacute;rale.</td>
      </tr>
      <tr>
        <td>`post-date-format`</td>
        <td>D&eacute;termine le format de date que vous souhaitez utiliser pour les noms de vos fichiers .md repr&eacute;sentant vos messages; par d&eacute;faut aaaa-mm-jj.</td>
      </tr>
      <tr>
        <td>`rss-name`</td>
        <td>Nom du fichier rss g&eacute;n&eacute;r&eacute;; par d&eacute;faut rss.xml.</td>
      </tr>
      <tr>
        <td>`rss-filters`</td>
        <td>Tags sp&eacute;cfiques pour lesquelles vous voulez qu&apos;un flux RSS soit g&eacute;n&eacute;r&eacute;.</td>
      </tr>
      <tr>
        <td>`sass-src`</td>
        <td>R&eacute;pertoire contenant les fichiers sass (sccs) &agrave; compiler; par d&eacute;faut &quot;css&quot;. Assurez-vous d&apos;inclure ce r&eacute;pertoire dans la section `resources`.</td>
      </tr>
      <tr>
        <td>`sass-dest`</td>
        <td>R&eacute;pertoire dans lequel les fichiers sass compil&eacute;s seront cr&eacute;&eacute;s; par d&eacute;faut &quot;css&quot;. Assurez-vous d&apos;inclure ce r&eacute;pertoire dans la section `resources`.</td>
      </tr>
      <tr>
        <td>`resources`</td>
        <td>Un vecteur reprenant le nom des r&eacute;pertoires et des fichiers &agrave; copier depuis `template` vers `public` lors de la compilation.</td>
      </tr>
      <tr>
        <td>`keep-files`</td>
        <td>Lors du nettoyage du r&eacute;pertoire `public`, les r&eacute;pertoires et fichiers list&eacute;s ne seront pas effac&eacute;s; par exemple vous pouvez garder votre r&eacute;pertoire `.git` si vous planifiez de publier sur GitHub Pages depuis le r&eacute;pertoire `public`.</td>
      </tr>
      <tr>
        <td>`disqus?`</td>
        <td>Positionnez &agrave; `true` si vous souhaitez incorporer Disqus dans votre site; par d&eacute;faut &agrave; `false`.</td>
      </tr>
      <tr>
        <td>`disqus-shortname`</td>
        <td>Votre compte Disqus.</td>
      </tr>
      <tr>
        <td>`ignored-files`</td>
        <td>Expression r&eacute;guli&egrave;re  correspondant &agrave; des fichiers que vous voulez ignorer lors de la compilation. Par exemple, les fichiers interlock d&apos;Emacs.</td>
      </tr>
    </tbody>
</table>

En plus de ces options de configuration par d&eacute;faut, vous pouvez ajouter vos propres options. Par exemple, si votre blog dispose d&apos;un sous-titre que vous souhaitez afficher sur votre site:&NewLine;
  1. Ajoutez `:sous-titre "Mon sous-titre"` au fichier de configuration
  2. Ins&eacute;rez votre sous-titre dans votre mod&egrave;le en utilisant `{% sous-titre %}` (Selmer)
