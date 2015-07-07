{:title "Bienvenue"
:layout :page
:page-index 0
:section "D&eacute;marrer"}

Ce site se veut &ecirc;tre un guide complet pour Cryogen. J&apos;ambitionne de couvrir comment installer et d&eacute;marrer votre site, cr&eacute;er et g&eacute;rer son contenu et sa pr&eacute;sentation, param&eacute;trer l&apos;esth&eacute;tique et ses fonctionnalit&eacute;s, et, finalement, comment le d&eacute;ployer.

##Qu&apos;est-ce que Cryogen?

Cryogen est un g&eacute;n&eacute;rateur de site statique simple &eacute;crit en Clojure. Comme il est disponible avec Leiningen, son installation est facile et ne n&eacute;cessite pas de t&acirc;tonner avec une quelconque base de donn&eacute;es ou d&apos;autres syst&egrave;mes de gestion de contenus (CMS).

Cryogen parcourt un r&eacute;pertoire dans lequel se trouve votre contenu au format Markdown, le convertit en HTML et l&apos;injecte dans vos mod&egrave;les (templates) &agrave; l&apos;aide de [Selmer](https://GitHub.com/yogthos/selmer). Il g&eacute;n&egrave;re alors un site complet pr&ecirc;t &agrave; publier contenant une carte du site et un flux RSS.

Si en parcourant ce guide vous voyez un point non couvert, vous pouvez [ouvrir une question](https://github.com/cryogen-project/cryogen/issues/new) sur la page GitHub et d&apos;autres instructions pourront alors &ecirc;tre incluses dans ce guide.
