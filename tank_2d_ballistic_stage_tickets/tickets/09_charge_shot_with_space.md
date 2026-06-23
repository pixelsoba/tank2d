# Ticket 09 — Charger le tir avec la barre espace

## Objectif

Quand le joueur maintient espace, la charge augmente. Quand il relâche espace, la charge revient à zéro temporairement.

## Contexte

Avant de tirer un projectile, on prépare la mécanique de charge.

## À faire

- [ ] Configurer l'action d'input `fire`.
- [ ] Associer `fire` à la barre espace.
- [ ] Dans `tank.gd`, ajouter `current_charge`, `max_charge`, `charge_speed`.
- [ ] Détecter si l'action `fire` est maintenue.
- [ ] Augmenter la charge pendant que l'action est maintenue.
- [ ] Remettre la charge à 0 quand l'action est relâchée.
- [ ] Envoyer la valeur de charge au HUD.
- [ ] Vérifier que la barre monte pendant l'appui.

Variables possibles :

```gdscript
@export var max_charge: float = 1.0
@export var charge_speed: float = 0.7

var current_charge: float = 0.0
var was_fire_pressed: bool = false
```

Code possible :

```gdscript
func update_charge(delta: float) -> void:
	var is_fire_pressed := Input.is_action_pressed("fire")

	if is_fire_pressed:
		current_charge += charge_speed * delta
		current_charge = clamp(current_charge, 0.0, max_charge)

	if was_fire_pressed and not is_fire_pressed:
		current_charge = 0.0

	was_fire_pressed = is_fire_pressed
```

## Critères de validation

- [ ] Maintenir espace augmente la charge.
- [ ] La barre de charge reflète la charge.
- [ ] Relâcher espace remet la charge à zéro.
- [ ] La charge ne dépasse pas la valeur maximum.
- [ ] Le projet se lance sans erreur.

## Commit attendu

```text
Charge shot with space
```
