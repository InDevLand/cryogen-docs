{:title "Configuration"
 :layout :post
 :page-index 3
 :section "D&eacute;marrer"}

Cryogène offre des options de configuration flexibles. Le fichier de configuration de votre site se trouve dans le répertoire `templates/config.edn` et contient les valeurs suivantes:

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
      <th>Mot-clé</th>
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
      <td>Un texte de présentation décrivant votre site</td>
      </tr>
      <tr>
        <td>`site-url`</td>
        <td>L'url de base de votre site. Cette valeur est utilisée pour générer la carte du site et le flux RSS.</td>
      </tr>
      <tr>
        <td>`post-root`</td>
        <td>Le répertoire dans lequel le compilateur cherche les articles. Cette valeur est insérée devant l'uri de tous les articles. Elle doit être fournie.</td>
      </tr>
      <tr>
        <td>`tag-root`</td>
        <td>Cette valeur est insérée devant l'uri des pages de tag. Elle doit être fournie.</td>
      </tr>
      <tr>
        <td>`page-root`</td>
        <td>Le répertoire dans lequel le compilateur cherche les pages. Cette valeur est insérée devant l'uri de toutes les pages. Elle doit être fournie.</td>
      </tr>
      <tr>
        <td>`blog-prefix`</td>
        <td>Cette valeur est insérée devant l'uri des articles. Elle doit être fournie.</td>
      </tr>
      <tr>
        <td>`recent-posts`</td>
        <td>Le nombre maximum d'articles récents à montre dans la barre latérale.</td>
      </tr>
      <tr>
        <td>`post-date-format`</td>
        <td>Détermine le format de date que vous souhaitez utiliser pour les noms de vos fichiers .md représentant vos messages; par défaut aaaa-mm-jj.</td>
      </tr>
      <tr>
        <td>`rss-name`</td>
        <td>Nom du fichier rss généré; par défaut rss.xml.</td>
      </tr>
      <tr>
        <td>`rss-filters`</td>
        <td>Tags spécfiques pour lesquelles vous voulez qu'un flux RSS soit généré.</td>
      </tr>
      <tr>
        <td>`sass-src`</td>
        <td>Répertoire contenant les fichiers sass (sccs) à compiler; par défaut "css". Assurez-vous d'inclure ce répertoire dans la section `resources`.</td>
      </tr>
      <tr>
        <td>`sass-dest`</td>
        <td>Répertoire dans lequel les fichiers sass compilés seront créés; par défaut "css". Assurez-vous d'inclure ce répertoire dans la section `resources`.</td>
      </tr>
      <tr>
        <td>`resources`</td>
        <td>Un vecteur reprenant le nom des répertoires et des fichiers à copier depuis `template` vers `public` lors de la compilation.</td>
      </tr>
      <tr>
        <td>`keep-files`</td>
        <td>Lors du nettoyage du répertoire `public`, les répertoires et fichiers listés ne seront pas effacés; par exemple vous pouvez garder votre répertoire `.git` si vous planifiez de publier sur GitHub Pages depuis le répertoire `public`.</td>
      </tr>
      <tr>
        <td>`disqus?`</td>
        <td>Positionnez à `true` si vous souhaitez incorporer Disqus dans votre site; par défaut à `false`.</td>
      </tr>
      <tr>
        <td>`disqus-shortname`</td>
        <td>Votre compte Disqus.</td>
      </tr>
      <tr>
        <td>`ignored-files`</td>
        <td>Expression régulière  correspondant à des fichiers que vous voulez ignorer lors de la compilation. Par exemple, les fichiers interlock d'Emacs.</td>
      </tr>
    </tbody>
</table>

En plus de ces options de configuration par défaut, vous pouvez ajouter vos propres options. Par exemple, si votre blog dispose d'un sous-titre que vous souhaitez afficher sur votre site:

  1. Ajoutez `:sous-titre "Mon sous-titre"` au fichier de configuration
  2. Insérez votre sous-titre dans votre modèle en utilisant `{% sous-titre %}` (Selmer)
