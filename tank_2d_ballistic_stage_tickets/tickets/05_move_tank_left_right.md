# Ticket 05 — Déplacer le tank gauche/droite

## Objectif

Faire se déplacer le tank à gauche et à droite sur la plateforme.

## Contexte

En Godot 4, pour un objet contrôlé avec collision, on utilise `CharacterBody2D`, sa propriété `velocity`, puis `move_and_slide()`.

## À faire

- [x] Configurer les actions d'input : `move_left`, `move_right`.
- [x] Associer `move_left` à gauche, A ou Q.
- [x] Associer `move_right` à droite ou D.
- [x] Ajouter une variable exportée `move_speed`.
- [x] Ajouter une variable exportée `gravity`.
- [x] Dans `_physics_process(delta)`, lire l'axe gauche/droite.
- [x] Modifier `velocity.x`.
- [x] Appliquer la gravité sur `velocity.y`.
- [x] Appeler `move_and_slide()`.
- [x] Vérifier que le tank ne traverse pas la plateforme.

Code possible :

```gdscript
extends CharacterBody2D

@export var move_speed: float = 180.0
@export var gravity: float = 900.0

func _physics_process(delta: float) -> void:
	var input_axis := Input.get_axis("move_left", "move_right")

	velocity.x = input_axis * move_speed

	if not is_on_floor():
		velocity.y += gravity * delta
	else:
		velocity.y = 0.0

	move_and_slide()
```

## Critères de validation

- [x] Le tank se déplace à gauche.
- [x] Le tank se déplace à droite.
- [x] Le tank reste posé sur la plateforme.
- [x] Le code utilise `velocity`.
- [x] Le code utilise `move_and_slide()`.
- [x] Le projet se lance sans erreur.
## Commit attendu

```text
Move tank left and right
```

## Notes

Oui, en 2D Godot 4, c'est bien `CharacterBody2D` + `velocity` + `move_and_slide()`.
