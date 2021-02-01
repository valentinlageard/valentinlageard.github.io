---
layout: post
title: Cartographier la philosophie
permalink: /carte-philo
---

Récemment, alors que je faisais des recherches sur [Philpapers](http://philpapers.org), j'ai pu constaté la richesse et le détail de leur [page des catégories](http://philpapers.org/browse/all) et une idée m'est venue.

Et si j'utilisais cette taxonomie fantastiquement exhaustive pour produire une **carte taxinomique de la philosophie**. L'idée m'a paru intéressante est je me suis mis au travail.

La première étape fut de sélectionner le type de graphique à utiliser et puisque la taxonomie de Philpapers inclut une hiérarchie permettant à des sous-catégories d'appartenir à plusieurs catégories parentes, je me suis dit qu'un réseau dirigé en cercles concentriques serait pertinent avec chaque cercle représentant un niveau dans la relation parent/enfant. Habitué de python, j'ai opté pour [NetworkX](https://networkx.github.io/) pour créer mon graph. J'ai utilisé [BeautifulSoup](https://www.crummy.com/software/BeautifulSoup/bs4/doc/)[^fn-beautsoup] pour scraper le contenu de la page et une fonction codée maison pour traduire le contenu du site en graph networkx. De plus, puisque Philpapers nous donne aussi le nombre d'articles par catégorie, je me suis dit qu'il serait intéressant si la taille des noeuds correspondait à la quantité d'articles dans la catégorie associée à ce noeud.

Après un long paramétrage du graph et la modification de la fonction d'affichage des labels de networkx, j'ai abouti au but tant désiré : une **représentation graphique de la taxonomie de la philosophie**.

![philosophy map network taxonomy](/images/philo4layersthumbnail.jpg)
*[Télécharger l'image (3Mo)](/images/philo4layers.svg)*

Dans cette première version simplifiée, il n'y a que 4 niveaux de hiérarchie (sans compter le noeud central). Si on rajoute le 5<sup>ème</sup> niveau, la carte devient sensiblement plus détaillée.

![philosophy map network taxonomy](/images/philo5layersthumbnail.jpg)
*[Télécharger l'image (11.9Mo)](/images/philo5layers.svg)*

Au premier regard on a l'impression de se tenir devant un antique rêve de philosophe enfin réalisé.

On trouve la représentation de certains biais culturels comme par exemple que l'Asie semble intéresser bien plus que l'Afrique.

![philosophy map network african oriental](https://github.com/valentinlageard/valentinlageard.github.io/raw/master/images/philoafroasia.jpg)

On apprend que le féminisme a une taxinomie fournie sur l'arbre philosophique.

![philosophy map network feminism](https://github.com/valentinlageard/valentinlageard.github.io/raw/master/images/philofeminism.jpg)

Et on découvre la zone des thèmes qui m'intéressent.

![philosophy map network computation consciousness](https://github.com/valentinlageard/valentinlageard.github.io/raw/master/images/philocool.jpg)

![philosophy map network consciousness ](https://github.com/valentinlageard/valentinlageard.github.io/raw/master/images/philoconscious.jpg)

[^fn-beautsoup]: Qui est par ailleurs un scraper python très intuitif et facile à maitriser que je recommande à tous.
