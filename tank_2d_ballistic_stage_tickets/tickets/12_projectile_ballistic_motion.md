# Ticket 12 — Appliquer un mouvement balistique au projectile

## Objectif

Faire suivre au projectile une trajectoire courbe sous l'effet de la gravité.

## Contexte

Le projectile doit recevoir une vitesse initiale, puis être accéléré vers le bas par la gravité.

## À faire

- [ ] Dans `projectile.gd`, ajouter une variable exportée `gravity`.
- [ ] Ajouter une fonction `launch(initial_velocity: Vector2)`.
- [ ] Dans `_process(delta)`, appliquer la gravité.
- [ ] Déplacer le projectile avec `position += velocity * delta`.
- [ ] Dans `Main.gd`, calculer la puissance du tir.
- [ ] Appeler `projectile.launch(shot_direction * shot_power)`.
- [ ] Supprimer le projectile s'il sort trop loin de l'écran ou après une durée maximale.

Code `projectile.gd` possible :

```gdscript
extends Area2D

@export var gravity: Vector2 = Vector2(0.0, 900.0)
@export var max_lifetime: float = 5.0

var velocity: Vector2 = Vector2.ZERO
var lifetime: float = 0.0

func launch(initial_velocity: Vector2) -> void:
	velocity = initial_velocity

func _process(delta: float) -> void:
	lifetime += delta
	velocity += gravity * delta
	position += velocity * delta

	if lifetime > max_lifetime:
		queue_free()
```

Code `Main.gd` possible :

```gdscript
@export var projectile_scene: PackedScene
@export var min_shot_power: float = 300.0
@export var max_shot_power: float = 900.0

@onready var projectiles_root: Node2D = $Projectiles

func on_tank_shot_requested(spawn_position: Vector2, direction: Vector2, charge_ratio: float) -> void:
	var projectile := projectile_scene.instantiate()
	projectile.global_position = spawn_position

	var shot_power := lerp(min_shot_power, max_shot_power, charge_ratio)

	if projectile.has_method("launch"):
		projectile.launch(direction * shot_power)

	projectiles_root.add_child(projectile)
```

## Critères de validation

- [ ] Le projectile part dans la direction du canon.
- [ ] Plus la charge est élevée, plus le projectile part vite.
- [ ] Le projectile tombe sous l'effet de la gravité.
- [ ] La trajectoire est courbe.
- [ ] Le projectile disparaît après quelques secondes.
- [ ] Le projet se lance sans erreur.

## Commit attendu

```text
Add ballistic projectile motion
```
