# Ticket 11 — Tirer un projectile au relâchement de la barre espace

## Objectif

Quand le joueur relâche espace après avoir chargé, créer un projectile.

## Contexte

Ce ticket connecte le tank, la charge et la scène projectile.

## À faire

- [ ] Dans `Main.tscn`, vérifier qu'il existe un node `Projectiles`.
- [ ] Dans `Tank.tscn`, ajouter un node `Muzzle` de type `Marker2D` au bout du canon.
- [ ] Créer un signal dans `tank.gd` :

```gdscript
signal shot_requested(spawn_position: Vector2, direction: Vector2, charge_ratio: float)
```

- [ ] Quand espace est relâché, émettre ce signal.
- [ ] Dans `Main.gd`, écouter ce signal.
- [ ] Instancier `Projectile.tscn`.
- [ ] Placer le projectile à `spawn_position`.

## Direction du tir

```gdscript
var shot_direction := Vector2(cos(turret_angle), sin(turret_angle)).normalized()
```

## Exemple émission signal

```gdscript
if was_fire_pressed and not is_fire_pressed:
	var charge_ratio := current_charge / max_charge
	var shot_direction := Vector2(cos(turret_angle), sin(turret_angle)).normalized()
	shot_requested.emit(muzzle.global_position, shot_direction, charge_ratio)
	current_charge = 0.0
```

## Critères de validation

- [ ] Le tank possède un `Muzzle`.
- [ ] Relâcher espace crée un projectile.
- [ ] Le projectile apparaît au bout du canon.
- [ ] Le projectile est ajouté sous le node `Projectiles`.
- [ ] Le projet se lance sans erreur.

## Commit attendu

```text
Fire projectile on space release
```
