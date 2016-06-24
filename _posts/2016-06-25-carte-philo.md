---
layout: post
title: Cartographier la philosophie
---

Récemment, je trainais sur [philpapers](http://philpapers.org) comme tout bon étudiant en philo qui est en rush sur ses rendus et à un moment donné je me suis arrêté sur leur page de catégorie et je me suis dit que c'était fou à quel point leur taxonomie était détaillée. Et puis d'un coup une idée m'a frappé.

Et si j'utilisais cette taxonomie fantastiquement exhaustive pour faire une **carte de la philosophie**. Je me suis dit que c'était une idée fantastique et je me suis mis au travail.

La première étape fut de sélectionner quel type de graphique utiliser et puisque la taxonomie de Philpapers inclut une hiérarchie permettant à des sous-catégories d'appartenir à plusieurs catégories parentes, je me suis dit qu'un réseau en cercles concentriques serait pas mal. Vu que j'utilise python, j'ai opté pour [NetworkX](https://networkx.github.io/) pour créer mon graph. J'ai utilisé [BeautifulSoup](https://www.crummy.com/software/BeautifulSoup/bs4/doc/)[^fn-1] pour scraper le contenu de la page et j'ai utilisé une fonction codée maison pour traduire le contenu du site en graph networkx. De plus, puisque Philpapers nous donne aussi le nombre d'articles par catégorie, je me suis dit que ce serait une donnée intéressante si la taille des noeuds/catégories dépendait du nombre d'article de cette catégorie et j'ai aussi aggrégé cette donnée.

Après un long paramétrage du graph à l'empirique et la modification de la fonction d'affichage des labels de networkx, j'ai abouti au but tant désiré : une **représentation graphique de la taxonomie de la philosophie**. Et c'était beau.

![philosophy map network taxonomy](https://github.com/valentinlageard/valentinlageard.github.io/raw/master/images/philo4layers.jpg)

Et ça encore c'est pas tout, il n'y a ici que 4 niveaux de hiérarchie (sans compter le noeud central). Si on rajoute le 5^ème^ ça devient beaucoup plus détaillé (et beaucoup moins lisible).

![philosophy map network taxonomy](https://github.com/valentinlageard/valentinlageard.github.io/raw/master/images/graph5layersdebugeddown.jpg)

Au premier regard on a l'impression de se tenir devant un vieux rêve de philosophe enfin réalisé. Et puis on parcourt les branches en partant du centre et l'on découvre des choses intéressantes et gratifiantes comme par exemple que la continentalité est classée comme tradition contrairement à la philosophie analytique qui n'est pas considérée comme une tradition.

On trouve la représentation de certains biais culturels comme par exemple que l'Asie semble intéresser bien plus que l'Afrique.

![philosophy map network african oriental](https://github.com/valentinlageard/valentinlageard.github.io/raw/master/images/philoafroasia.jpg)

On apprend que le féminisme se porte très bien en philosophie et a une place légitime bien fournie sur l'arbre philosophique.

![philosophy map network feminism](https://github.com/valentinlageard/valentinlageard.github.io/raw/master/images/philofeminism.jpg)

On trouve la zone des trucs intéressants.

![philosophy map network computation consciousness](https://github.com/valentinlageard/valentinlageard.github.io/raw/master/images/philocool.jpg)

![philosophy map network consciousness ](https://github.com/valentinlageard/valentinlageard.github.io/raw/master/images/philoconscious.jpg)

Et on repère très rapidement la zone du bullshit.

![philosophy map network bullshit Derrida](https://github.com/valentinlageard/valentinlageard.github.io/raw/master/images/philobullshit.jpg)

On apprend que Wittgenstein pèse plus que Nietzsche.

![philosophy map network wittgenstein nietzsche](https://github.com/valentinlageard/valentinlageard.github.io/raw/master/images/philowittgynietzsche.jpg)

Enfin, on note la petite place mais néanmoins existante de la philosophie de la drogue.

![philosophy map network drugs](https://github.com/valentinlageard/valentinlageard.github.io/raw/master/images/philodrugs.jpg)

Mais surtout ce que l'on apprend, c'est une certaine humilité face à une telle immensité. On expérimente une forme de sentiment proche du [*sonder*](http://www.dictionaryofobscuresorrows.com/post/23536922667/sonder) mais où la multitude des agents aurait été remplacée par la multitude des connaissances et des thèmes de recherche. On en vient à ressentir profondément l'intuition socratique de notre propre ignorance et malgré le désespoir qu'elle nous inspire, le sentiment de sagesse l'accompagnant nous rassure et nous donne du courage pour parcourir cet arbre à la manière d'un singe, habile et précis dans ses mouvements.

[^fn-1]: Qui est par ailleurs un scraper python très intuitif et facile à maitriser que je recommande à tous.
