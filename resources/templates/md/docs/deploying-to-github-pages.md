{:title "GitHub Pages"
 :layout :page
 :page-index 6
 :section "D&eacute;ploiement"}

[Les Pages GitHub](https://pages.GitHub.com/) permettent l&apos;h&eacute;bergement gratuit de sites dans le domaine `github.io` appartenant &agrave; GitHub. Normalement, ces sites sont produits &agrave; l&apos;aide de [Jekyll](http://jekyllrb.com) mais comme les Pages GitHub supportent le contenu HTML, il est possible d&apos;&eacute;galement h&eacute;berger votre site &agrave; l&apos;aide de Cryogen.

GitHub propose deux types d&apos;h&eacute;bergement de base: *les pages utilisateur/organisation* et *les pages projet*. Chacun d&apos;eux fonctionne en se basant sur des branches sp&eacute;cifiques de vos d&eacute;p&ocirc;ts sur GitHub. La fa&ccedil;on de d&eacute;ployer ces deux types de sites est semblable et diff&egrave;re uniquement dans la configuration de d&eacute;part.

## Configurer les pages Utilisateurs et Organisation

Les pages Utilisateurs et Organisation doivent r&eacute;sider dans un d&eacute;p&ocirc;t GitHub sp&eacute;cifiquement d&eacute;di&eacute; &agrave; cela. Ce d&eacute;p&ocirc;t doit s&apos;appeler *utilisateur*.GitHub.io. *utilisateur* est votre compte GitHub ou le nom  de l&apos;organisation. Par exemple, `lacarmen.GitHub.io`.

Le contenu de la branche `master` de votre d&eacute;p&ocirc;t sera utilis&eacute; pour construire et publier votre site sur vos pages GitHub.

Si vous souhaitez cr&eacute;er des pages utilisateur ou organisation avec Cryogen, assurez-vous que le champ de l&apos;option `blog-prefix` dans le fichier de configuration est vide.

## Configurer les pages Projet

Contrairement aux pages utilisateur/organisation, les pages Projet r&eacute;sident dans le m&ecirc;me d&eacute;p&ocirc;t que le projet lui-m&ecirc;me, si ce n&apos;est que le contenu se trouve dans une branche sp&eacute;cifique appel&eacute;e `gh-pages`. Le contenu est alors disponible dans un sous-chemin du domaine de vos pages utilisateur, par exemple `lacarmen.GitHub.io/cryogen`.

Le d&eacute;p&ocirc;t cryogen est un bon exemple de cette structure. La [branche master](https://GitHub.com/lacarmen/cryogen/tree/master) le mod&egrave;le standard lein-template pour Cryogen tandis que le site web que vous consultez en ce moment est contenu dans la [branche gh-pages](https://GitHub.com/lacarmen/cryogen/tree/gh-pages) du m&ecirc;me d&eacute;p&ocirc;t.

Si vous souhaitez utiliser Cryogen pour cr&eacute;er un site pour votre projet, assurez-vous que le champ de l&apos;option `blog-prefix` dans le fichier de configuration corresponde au nom de d&eacute;p&ocirc;t de votre projet.

### Créer la branche gh-pages

Pour cr&eacute;er la branche pour les pages de votre projet, vous devez cr&eacute;er une nouvelle branche &quot;orpheline&quot;.

La mani&egrave;re la plus sure d&apos;y parvenir est de cr&eacute;er un nouveau clone de votre d&eacute;p&ocirc;t.

```
$ git clone https://GitHub.com/user/repository.git
# Clôner votre d&eacute;p&ocirc;t
```

Une fois que vous avez un nouveau d&eacute;p&ocirc;t, il est n&eacute;cessaire de cr&eacute;er la branche `gh-pages` et la vider de son contenu.

```
$ cd repository

$ git checkout --orphan gh-pages
# Cr&eacute;e une branche sans parents
# Postionnement dans la nouvelle branche 'gh-pages'

$ git rm -rf .
# Supprime tous les fichiers de l'ancienne branche
# rm .gitignore
```


## D&eacute;ployer sur GitHub Pages

Une fois que vous avez configur&eacute; votre d&eacute;p&ocirc;t pour le type de pages GitHug que vous souhaitez, copiez vos fichiers et r&eacute;pertoires dans le r&eacute;pertoire principal de votre site - `public` si vous cr&eacute;ez des pages Utilisateur; `public/NOM-DU-DEPOT-DE-VOTRE-PROJET` si vous cr&eacute;ez des pages Projet.

La derni&egrave;re &eacute;tape consiste &agrave; pousser votre contenu vers GitHub.

```
$ git add *
$ git commit -a -m "Commit initial pages"
$ git push origin gh-pages
```

Si vous apportez des modifications &agrave; votre site, suivez simplement ces &eacute;tapes de d&eacute;ploiement pour mettre &agrave; jour vos pages GitHub.
