# Ticket 05 — Déplacer le tank gauche/droite

## Objectif

Faire se déplacer le tank à gauche et à droite sur la plateforme.

## Contexte

En Godot 4, pour un objet contrôlé avec collision, on utilise `CharacterBody2D`, sa propriété `velocity`, puis `move_and_slide()`.

## À faire

- [ ] Configurer les actions d'input : `move_left`, `move_right`.
- [ ] Associer `move_left` à gauche, A ou Q.
- [ ] Associer `move_right` à droite ou D.
- [ ] Ajouter une variable exportée `move_speed`.
- [ ] Ajouter une variable exportée `gravity`.
- [ ] Dans `_physics_process(delta)`, lire l'axe gauche/droite.
- [ ] Modifier `velocity.x`.
- [ ] Appliquer la gravité sur `velocity.y`.
- [ ] Appeler `move_and_slide()`.
- [ ] Vérifier que le tank ne traverse pas la plateforme.

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

- [ ] Le tank se déplace à gauche.
- [ ] Le tank se déplace à droite.
- [ ] Le tank reste posé sur la plateforme.
- [ ] Le code utilise `velocity`.
- [ ] Le code utilise `move_and_slide()`.
- [ ] Le projet se lance sans erreur.

## Commit attendu

```text
Move tank left and right
```

## Notes

Oui, en 2D Godot 4, c'est bien `CharacterBody2D` + `velocity` + `move_and_slide()`.
