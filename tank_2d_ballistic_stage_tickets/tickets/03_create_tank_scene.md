# Ticket 03 — Créer la scène Tank

## Objectif

Créer une scène `Tank.tscn` basée sur `CharacterBody2D`.

## Contexte

Le tank doit pouvoir se déplacer sur la plateforme avec la physique 2D de Godot.

## À faire

- [x] Créer une scène `Tank.tscn`.
- [x] Sauvegarder la scène dans `scenes/`.
- [x] Utiliser un node racine de type `CharacterBody2D`.
- [x] Renommer le node racine en `Tank`.
- [x] Ajouter un enfant `CollisionShape2D`.
- [x] Utiliser une forme de collision simple, par exemple `RectangleShape2D`.
- [x] Ajouter un enfant `BodyVisual` de type `Sprite2D` ou `ColorRect`.
- [x] Ajouter un enfant `TurretPivot` de type `Node2D`.
- [x] Sous `TurretPivot`, ajouter `BarrelVisual` de type `Sprite2D`, `ColorRect` ou `Line2D`.
- [x] Créer un script `scripts/tank.gd`.
- [x] Attacher le script au node `Tank`.
- [x] Instancier `Tank.tscn` dans `Main.tscn`, sous `World`.

Structure attendue :

```text
Tank (CharacterBody2D)
├── CollisionShape2D
├── BodyVisual
└── TurretPivot (Node2D)
    └── BarrelVisual
```

Script minimal :

```gdscript
extends CharacterBody2D

func _ready() -> void:
	print("Tank ready")
```

## Critères de validation

- [x] `scenes/Tank.tscn` existe.
- [x] Le node racine est un `CharacterBody2D`.
- [x] Le tank est visible dans `Main.tscn`.
- [x] Le tank possède une collision.
- [x] Le projet se lance sans erreur.
## Commit attendu

```text
Add tank scene
```
