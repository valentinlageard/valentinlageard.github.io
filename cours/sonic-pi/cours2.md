# Aléatoire et options (Cours II)

## Comprendre les loops

1. Quelle est la différence entre : 
```rb {.line-numbers}
live_loop :melodie do
	play 60
	sleep 1
	play 72
end
```

et :

```rb {.line-numbers}
live_loop :melodie do
	play 60
	sleep 1
	play 72
	sleep 1
end
```

<iframe width="640" height="360" src="https://www.youtube.com/embed/iFMNOb33_KM" frameborder="0" allowfullscreen></iframe>

---

## Synths

1. Fais une boucle `:melodie` et execute la.
2. Au début de ta boucle, dans celle-ci, ajoute :
```rb  {.line-numbers}
use_synth :piano
```
et execute le code à nouveau. Qu'est-ce qui a changé.
3. Juste après avoir tapé `use_synth`, l'ide te propose divers synths. Essaies en plusieurs pour voir comment il sonnent. Tu peux par exemple essayer `:pluck`, `:prophet`, `:dsaw`, etc...
4. A ton avis, qu'est-ce qu'un synth ?

---

## Options des synth

Les synths ont plusieurs options qui modifient leurs sons. Certains synths ont des options uniques mais la plupart d'entre-eux partagent des options de base.

---

## amp

1. Execute : 
```rb  {.line-numbers}
live_loop :melodie do
	use_synth :piano
	play 60, amp: 1
	sleep 1
end
```
Change le chiffre après `amp:` entre 0 et 1 et execute à nouveau. Que se passe-t-il ? A quoi sert `amp` ?

---

## pan

1. Execute : 
```rb  {.line-numbers}
live_loop :melodie do
	use_synth :piano
	play 60, pan: 0
	sleep 1
end
```
Change le chiffre après `pan:` entre -1 et 1 et execute à nouveau. Que se passe-t-il ? A quoi set `pan` ?

---

## release
1. Execute :
```rb  {.line-numbers}
live_loop :melodie do
	use_synth :piano
	play 60, release: 1
	sleep 1
end
```
Change le chiffre après `release:` entre 0 et 2 par exemple. Que se passe-t-il ? A quoi sert `release` ?

---

## attack 

1. Execute :
```rb  {.line-numbers}
live_loop :melodie do
	use_synth :piano
	play 60, attack: 0
	sleep 1
end
```
Change le chiffre après `attack:` entre 0 et 2 par exemple. Que se passe-t-il ? A quoi sert `attack` ?

---

## Envelope simplifiée

Une envelope décrit comment le volume d'un son va monter puis descendre. L'attack est le temps qu'il faut pour que le volume de la note monte et la release est le temps qu'il faut pour qu'il descende. 

@import "img/envelope.jpg"

---

## Combiner les options

1. Execute :
```rb  {.line-numbers}
live_loop :melodie do
	use_synth :piano
	play 60, amp: 1, pan: 0, attack: 0, release: 0
	sleep 1
end
```
Change en live les valeurs des options. Tu peux aussi changer le synth !

---


## Ajouter une batterie de base

1. Commençons par créer une boucle :
```rb {.line-numbers}
live_loop :batterie do
	sample :drum_heavy_kick
	sleep 0.5
	sample :drum_snare_hard
	sleep 0.5
end
```
2. Maintenant, ajoutons une cymbale :
```rb {.line-numbers}
live_loop :cymbale do
	sample :drum_cymbal_closed
	sleep 0.25
end
```

---

## Options et sample

1. Certaines options fonctionnent aussi avec sample. Dans ta ligne de cymbale ajoute `amp` et `pan` :
```rb {.line-numbers}
live_loop :cymbale do
	sample :drum_cymbal_closed, amp: 1
	sleep 0.25
end
```
Change en live la valeur de `amp` et de `pan` pour voir ce que ça fait.

---

## Choix aléatoire (sélection de sample)

Ces deux loops de batterie sont pas mal, mais elles sont un peu répétitives.

1. Execute le code suivant : 
```rb {.line-numbers}
live_loop :cymbale_aleatoire do
	sample choose([:drum_cymbal_closed, :drum_cymbal_open])
	sleep 0.125
end
```
Que se passe-t-il ? A quoi sert la fonction `choose` ?

---

## Choix aléatoire (sélection de temps)

1. On peut choisir le temps des notes. Execute le code suivant : 
```rb {.line-numbers}
live_loop :cymbale_aleatoire2 do
	sample :drum_cymbal_closed
	sleep choose([0.125,0.25])
end
```
Que se passe-t-il ? Qu'est ce que `[0.125, 0.25]`

---

## Choix aléatoire (sélection de notes)

1. On peut aussi uiliser `choose` pour sélectionner des notes. Execute le code suivant :
```rb {.line-numbers}
live_loop :melodie_aleatoire do
	play choose([60, 63, 67])
	sleep 0.5
end
```

---

## Une autre manière de choisir

1. Que va-t-il se passer si l'on execute le code suivant : 
```rb {.line-numbers}
live_loop :melodie_aleatoire do
	play [60, 63, 67].choose
	sleep 0.5
end
```

---

## print

1. Execute : 
```rb {.line-numbers}
print 1
```
Que se passe-t-il ?
2. Change le chiffre et execute à nouveau. Que se passe-t-il ?
3. Au lieu du chiffre écrit "salut monde" et execute à nouveau. Que se passe-t-il ?
4. A quoi sert print ?

---

## rrand
1. Execute : 
```rb {.line-numbers}
print rrand(0,1)
```
Que se passe-t-il ?
2. Execute : 
```rb {.line-numbers}
live_loop :aleatoire do
	print rrand(0,1)
end
```
Que se passe-t-il ?
2. Change les chiffres entre les parenthèses de rrand et execute à nouveau. Que se passe-t-il ? A quoi sert `rrand` ?
3. Fais une boucle `:melodie_aleatoire` qui joue à chaque fois une note aléatoire entre 60 et 72.

---

## rrand_i
1. Le problème avec rrand est qu'il génère des **floats** (des nombres avec virgule). Ce n'est pas très pratique pour générer des notes, pourquoi ?
2. Execute 
```rb {.line-numbers}
live_loop :aleatoire do
	print rrand(0,1)
end
```
Que se passe-t-il ?
3. Fais une boucle `melodie_aleatoire` qui joue à chaque fois une note aléatoire entre 60 et 72 en utilisant `rrand_i`

---

## rrand et les options
1. Si `rrand` n'est pas pratique pour générer des notes, il est pratique pour contrôler des options. Dans ta loop `:cymbale`, contrôle `amp` et `pan` avec rrand.
2. Dans ta loop `:melodie`, contrôle les options `attack` et `release` des notes que tu joue avec `rrand`. 

---

## Recapitulatif

Crée un morceau avec : 
- Une boucle `:batterie` avec `:drum_heavy_kick` et `:drum_hard_snare`.
- Une boucle `:cymbale` choisissant entre `:drum_cymbal_open` et `:drum_cymbal_open` et avec les options `amp` et `pan` contrôlées avec `rrand`
- Une boucle `:melodie` dont les notes sont aléatoirement choisies avec `choose` ou générées avec `rrand_i`.
- La boucle `:melodie` doit utiliser un synth avec `use_synth`
- Les options des notes de la boucle `:melodie` doivent être contrôlées avec `attack` et `release` avec `rrand` pour ajouter de la dynamique.
- Une ou plusieurs boucles supplémentaires de ta création.

---

[Retour à l'index](index.html)
