# Ticket 07 — Créer tourelle/canon et visée haut/bas

## Objectif

Permettre au joueur d'orienter le canon vers le haut ou vers le bas.

## Contexte

L'angle du canon servira à calculer la direction initiale du projectile.

## À faire

- [ ] Vérifier que `Tank.tscn` contient un node `TurretPivot`.
- [ ] Vérifier que `TurretPivot` contient un visuel de canon.
- [ ] Configurer les actions d'input : `aim_up`, `aim_down`.
- [ ] Associer `aim_up` à haut, W ou Z.
- [ ] Associer `aim_down` à bas ou S.
- [ ] Ajouter une variable exportée `aim_speed`.
- [ ] Ajouter des limites d'angle.
- [ ] Modifier la rotation de `TurretPivot`.
- [ ] Empêcher le canon de dépasser les limites.

Code possible :

```gdscript
@export var aim_speed: float = 1.5
@export var min_turret_angle: float = deg_to_rad(-80.0)
@export var max_turret_angle: float = deg_to_rad(-10.0)

@onready var turret_pivot: Node2D = $TurretPivot

var turret_angle: float = deg_to_rad(-45.0)

func update_aim(delta: float) -> void:
	var aim_axis := Input.get_axis("aim_up", "aim_down")

	turret_angle += aim_axis * aim_speed * delta
	turret_angle = clamp(turret_angle, min_turret_angle, max_turret_angle)

	turret_pivot.rotation = turret_angle
```

À appeler depuis `_physics_process(delta)` :

```gdscript
update_aim(delta)
```

## Critères de validation

- [ ] Le canon monte avec l'input haut.
- [ ] Le canon descend avec l'input bas.
- [ ] Le canon reste dans des limites raisonnables.
- [ ] L'angle est stocké dans une variable.
- [ ] Le projet se lance sans erreur.

## Commit attendu

```text
Add turret aiming
```
