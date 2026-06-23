# Notes math — Tir balistique simplifié

## Objectif

Quand le tank tire, on veut créer un projectile qui part :

- depuis la bouche du canon ;
- dans la direction du canon ;
- avec une vitesse initiale dépendant de la charge ;
- puis qui tombe sous l'effet de la gravité.

## Direction de tir depuis un angle

Si le canon a un angle `angle`, on peut créer une direction avec :

```gdscript
Vector2(cos(angle), sin(angle))
```

En Godot 2D :

- X positif va vers la droite ;
- Y positif va vers le bas ;
- un angle négatif pointe vers le haut.

Exemple :

```gdscript
var direction := Vector2(cos(turret_angle), sin(turret_angle)).normalized()
```

## Vitesse initiale

```gdscript
projectile_velocity = direction * shot_power
```

## Mouvement balistique

À chaque frame :

```gdscript
velocity += gravity_vector * delta
position += velocity * delta
```

Avec par exemple :

```gdscript
var gravity_vector := Vector2(0.0, 900.0)
```

## Charge de tir

Une charge simple peut aller de 0 à 1 :

```gdscript
charge_ratio = current_charge / max_charge
```

Puis :

```gdscript
shot_power = lerp(min_shot_power, max_shot_power, charge_ratio)
```

## À retenir

```gdscript
projectile.velocity = shot_direction * shot_power
velocity += gravity * delta
position += velocity * delta
```
