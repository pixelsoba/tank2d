# Ticket 14 — Détecter l'impact projectile/cible

## Objectif

Détecter quand un projectile touche la cible.

## Contexte

Le prototype doit fournir un feedback simple quand la cible est touchée.

## À faire

- [ ] Configurer les collisions du projectile et de la cible.
- [ ] Connecter le signal `area_entered`.
- [ ] Détecter si l'objet reçu est un projectile.
- [ ] Afficher un message dans la console.
- [ ] Changer le visuel de la cible quand elle est touchée.
- [ ] Supprimer le projectile après impact.

Code possible dans `target.gd` :

```gdscript
extends Area2D

var is_hit: bool = false

func _ready() -> void:
	area_entered.connect(_on_area_entered)

func _on_area_entered(area: Area2D) -> void:
	if is_hit:
		return

	if area.is_in_group("projectiles"):
		is_hit = true
		print("Target hit")
		area.queue_free()
```

Dans `projectile.gd` :

```gdscript
func _ready() -> void:
	add_to_group("projectiles")
```

## Critères de validation

- [ ] Un projectile peut toucher la cible.
- [ ] Un message est affiché à l'impact.
- [ ] Le projectile disparaît après impact.
- [ ] La cible change d'état ou de visuel.
- [ ] Le projet se lance sans erreur.

## Commit attendu

```text
Detect target hit
```
