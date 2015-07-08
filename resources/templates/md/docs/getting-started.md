{:title "D&eacute;marrer"
 :layout :page
 :page-index 1
 :section "D&eacute;marrer"}

Cryog&egrave;ne se veut aussi simple que possible. Il n&apos;est pas n&eacute;cessaire de mettre en place une base de donn&eacute;es ou faire des pieds et des mains juste pour cr&eacute;er un site g&eacute;n&eacute;rique.

Pour d&eacute;marrer, vous avez besoin que [Leiningen](http://leiningen.org/) soit install&eacute;. Une fois que c&apos;est fait, voici comment cr&eacute;er un site de base.


```
~ $ lein new cryogen mon-blog
~ $ cd mon-blog
~/mon-blog $ lein ring server
```

Lorsque le serveur est d&eacute;marr&eacute;, vous pouvez visiter votre site &agrave; l&apos;adresse [localhost:3000](http://localhost:3000). La premi&egrave;re chose que vous verrez est un README reprenant les &eacute;tapes suivantes.
