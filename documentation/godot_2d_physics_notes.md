# Notes Godot 2D — CharacterBody2D et move_and_slide

## Pour déplacer le tank

En Godot 4, pour un véhicule contrôlé en 2D, utiliser :

```gdscript
CharacterBody2D
```

Le node possède une propriété importante :

```gdscript
velocity
```

Pour déplacer le body avec la physique Godot :

```gdscript
move_and_slide()
```

En Godot 4, on écrit généralement :

```gdscript
velocity.x = input_axis * move_speed
velocity.y += gravity * delta
move_and_slide()
```

`move_and_slide()` utilise directement la propriété `velocity` du `CharacterBody2D`.

## Exemple simple

```gdscript
extends CharacterBody2D

@export var move_speed: float = 200.0
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

## Pourquoi `_physics_process` ?

Pour les objets avec collision, préférer `_physics_process(delta)` à `_process(delta)`.

## Plateforme

Une plateforme fixe peut être faite avec :

```text
StaticBody2D
└── CollisionShape2D
```

## Projectile

Pour ce prototype, le projectile peut être :

```text
Area2D
├── CollisionShape2D
└── Sprite2D
```

Et son déplacement peut être simulé manuellement :

```gdscript
velocity += gravity_vector * delta
position += velocity * delta
```
