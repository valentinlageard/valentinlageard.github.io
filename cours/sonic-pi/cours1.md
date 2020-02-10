# Introduction à Sonic Pi (Cours I)

---

## Installation du logiciel

1. Tous aller sur [sonic-pi.net](sonic-pi.net)
2. Télécharger le logiciel avec l'aide du prof.
3. Installer le logiciel avec l'aide du prof.
4. Lancer Sonic-Pi.

@import "img/algoravelogo.png"
@import "img/algorave.jpg"

Qu'est-ce qu'un langage de livecoding ?

Qu'est-ce que la culture algorave ?


---

## Introduction à l'interface

@import "img/ide.png"

- Play/Pause/Stop
- Oscillateur
- IDE
- Retour

---

## Hello note

1. Execute `play 60`.
2. Execute à nouveau en changeant le nombre après `play`. Quelle est la différence ?
3. Qu'est-ce qu'une note de musique et qu'est-ce que la gamme chromatique ?

@import "img/midinotes.png"

---

## Les ordis sont bêtes

1. Que va-t-il se passer si tu executes `playy 50` à ton avis ? Essaie pour voir.
2. Que va-t-il se passer si tu executes `joue 50` à ton avis ? Essaie pour voir.
3. Que va-t-il se passer si tu executes `50 play` à ton avis ? Essaie pour voir.
4. L'ordinateur ne comprend que les mots qu'il connaît (vocabulaire), s'il n'y a pas d'erreur d'écriture et si la phrase est correcte (les mots sont mis dans le bon sens).

---

## Mélodie et ordre des instructions

1. Executer : 
```rb  {.line-numbers}
play 60
play 72
```
2. Executer : 
```rb  {.line-numbers}
play 60
sleep 1
play 72
```
Quelle est la différence ? A quoi sert sleep ?
3. Change la nombre après `sleep` et execute le code. Que se passe-t-il ? A quoi sert le chiffre après sleep ?

---

## Ta propre mélodie
On peut ajouter autant de notes que l'on veut comme ceci. Fais ta propre mélodie !
```rb  {.line-numbers}
play 60
sleep 1
play 60
sleep 1
play 60
sleep 1
play 62
sleep 1
play 64
sleep 2
play 62
sleep 2
play 60
sleep 1
play 64
sleep 1
play 62
sleep 1
play 62
sleep 1
play 60
sleep 4
```

---

## Times

1. Execute :
```rb  {.line-numbers}
2.times do
	play 60
	sleep 1
	play 72
	sleep 1
end
```
Attention à la tabulation !
2. Change le chiffre avant times et execute à nouveau. A quoi sert times à ton avis ? 

---

## Boucles imbriquées

1. Execute :
```rb {.line-numbers}
2.times do
	play 60
	sleep 1
	play 62
	sleep 1
	3.times do
		play 64
		sleep 1
	end
	play 65
	sleep 1
end
```

Que se passe-t-il avec ce code ?

---

## Samples 

1. Execute :
```rb {.line-numbers}
sample :drum_hard_kick
sleep 1
sample :drum_hard_snare
sleep 1
```
Que se passe-t-il ?
2. Qu'est-ce qu'un sample ?

---

## Boucles infinies

1. Execute :
```rb {.line-numbers}
live_loop :beat do
	sample :drum_heavy_kick
	sleep 0.5
	sample :drum_snare_hard
	sleep 0.5
end
```
Que se passe-t-il ?
2. Compose un morceau avec plusieurs boucles.

---

## Notions à avoir compris : 
- Ecriture explicite : pas faire d'erreur, le programme comprend que son propre langage, ...
- Ordre des instructions.
- Répéter les instructions avec times.
- Utiliser des samples.
- Faire une boucle infinie avec live_loop.

---

[Retour à l'index](index.html)
