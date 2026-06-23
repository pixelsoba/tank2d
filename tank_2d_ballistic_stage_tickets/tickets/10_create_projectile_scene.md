# Ticket 10 — Créer la scène Projectile

## Objectif

Créer une scène réutilisable représentant un projectile.

## Contexte

Le projectile sera instancié quand le tank tire.

## À faire

- [ ] Créer une scène `Projectile.tscn`.
- [ ] Sauvegarder la scène dans `scenes/`.
- [ ] Utiliser un node racine de type `Area2D`.
- [ ] Renommer le node racine en `Projectile`.
- [ ] Ajouter un enfant `CollisionShape2D`.
- [ ] Utiliser une forme `CircleShape2D`.
- [ ] Ajouter un enfant `Visual` de type `Sprite2D` ou `ColorRect`.
- [ ] Créer un script `scripts/projectile.gd`.
- [ ] Attacher le script au node racine `Projectile`.
- [ ] Ajouter une variable `velocity`.

Structure attendue :

```text
Projectile (Area2D)
├── CollisionShape2D
└── Visual
```

Script minimal :

```gdscript
extends Area2D

var velocity: Vector2 = Vector2.ZERO
```

## Critères de validation

- [ ] `scenes/Projectile.tscn` existe.
- [ ] Le node racine est un `Area2D`.
- [ ] Le projectile possède une collision.
- [ ] Le projectile possède un visuel.
- [ ] Le script `projectile.gd` existe.
- [ ] Le projet se lance sans erreur.

## Commit attendu

```text
Add projectile scene
```
