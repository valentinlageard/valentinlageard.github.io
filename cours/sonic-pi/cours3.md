# Synths et Fx (Cours III)

## Session expérimentation

Faites une improvisation de 15-20 minutes avec ce qu'on a appris hier. Créez une ou plusieurs boucles `live_loop`.
Vous pouvez utiliser : 
- `play` ou `sample`
- `rrand` ou `rrand_i`
- `choose`
- `use_synth`
- Les options `amp`, `pan`, `attack`, `release`.

---

## Distortion

1. Execute : 
```rb {.line-numbers}
live_loop :melodie do
 	with_fx :distortion do
		play [60,63,67].choose
		sleep 0.5
	end
end
```
Que se passe-t-il ?

---

## Options d'effets

1. Si nous voulons augmenter/diminuer la distortion, il est possible d'ajouter une option. En effet les fx, comme les synths, ont des options.
2. Execute :
```rb {.line-numbers}
live_loop :melodie do
 	with_fx :distortion, distort: 0.7 do
		play [60,63,67].choose
		sleep 0.5
	end
end
```
Essaie diverses valeurs entre 0 et 1 !

---

## La documentation interne

1. Appuie sur Help / Aide.
2. Explore la documentation.

---

## Echo
 
1. Execute : 
```rb {.line-numbers}
live_loop :melodie do
 	with_fx :echo, phase: 0.25, decay: 2 do
		play [60,63,67].choose
		sleep 0.5
	end
end
```
2. Change les valeurs de phase et decay. Que contrôlent-elles ?

---

## Bitcrusher

1. Execute : 
```rb {.line-numbers}
live_loop :melodie do
 	with_fx :bitcrusher, bits: 8 do
		play [60,63,67].choose
		sleep 0.5
	end
end
```
2. Change la valeur de bits. Que contrôle-t-elle ?

---

## Octaver

1. Execute : 
```rb {.line-numbers}
live_loop :melodie do
 	with_fx :octaver, super_amp: 1, sub_amp: 1, subsub_amp: 1 do
		play [60,63,67].choose
		sleep 0.5
	end
end
```
2. Essaie les valeurs de `super_amp`, `sub_amp`et `subsub_amp` entre 0 et 1. Que contrôlent-t-elles ?

---

## D'autres fx

1. Va dans la documentation sur l'onglet Fx.
2. Essaie plusieurs fx et décide lequel est ton préféré.

---

## Session expérimentation

Faites une improvisation de 15-20 minutes avec ce qu'on a appris hier. Créez une ou plusieurs boucles `live_loop`.
Vous pouvez utiliser : 
- `play` ou `sample`
- `rrand` ou `rrand_i`
- `choose`
- `use_synth`
- Les options `amp`, `pan`, `attack`, `release`.
- Les divers fx et leurs options avec `with_fx`.

---

## Types d'objets

Dans Sonic-pi il y a plusieurs types d'objets : 
- Nombres entiers (INT) : `1`, `0`, `42`, etc...
- Nombre rationnels (FLOAT) : `0.58940`, `42.22222`
- Chaine de charactère (STRING) : `"salut ça va ?"`
- Liste (LIST) : `[0,1,2,3,4]`, `[:drum, :drum2]`
- Anneau (RING) : `(ring 1,2,3)`, `(ring :drum, :drum2)`

---

## Les anneaux et tick

1. Execute :
```rb {.line-numbers}
live_loop :melodie do
	play (ring 60, 63, 67).tick
	sleep 0.5
end
```
Que se passe-t-il ? Comment fonctionnent `ring` et `tick` ?

---

## Les chords
1. Execute : 
```rb {.line-numbers}
live_loop :arpeggio do
  play (chord :C, 'M').tick
  sleep 0.5
end
```
Que se passe-t-il ? A quoi sert `chord` ?
2. Au lieu de `:C`, essaie d'autres notes comme `:E` ou `:A`.
3. Au lieu de `M` (accord majeur), essaie `m` (accord mineur).
4. Va chercher dans la documentation des accords plus exotiques (`'m11'`, `madd9`, `dim7`, etc...) et choisis ton préféré.

---

## Les scales

1. Execute : 
```rb {.line-numbers}
live_loop :arpeggio do
  play (scale :C, :aeolian, num_octaves: 1).tick
  sleep 0.5
end
```
2. Essaie de changer la fondamentale de la gamme `:C` par une autre note (comme `:E` ou `:A` par exemple). Que se passe-t-il ?
3. Essaie de changer le chiffre après `num_octaves`. Que se passe-t-il ?
4. Essaie de changer la gamme utilisée `:aeolian` par une autre que tu peux trouver dans la documentation. Essaies en plusieurs et choisis ta préférée.

---

## Session expérimentation

Faites une improvisation de 15-20 minutes avec ce qu'on a appris hier. Créez une ou plusieurs boucles `live_loop`.
Vous pouvez utiliser : 
- `play` ou `sample`
- `rrand` ou `rrand_i`
- `choose`
- `use_synth`
- Les options `amp`, `pan`, `attack`, `release`.
- Les divers fx et leurs options avec `with_fx`.
- Les `ring`, `chord` et `scale` avec `tick`.
