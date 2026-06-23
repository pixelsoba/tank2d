# Ticket 02 — Créer la plateforme

## Objectif

Créer une plateforme fixe sur laquelle le tank pourra se déplacer.

## Contexte

La plateforme sert de sol. Elle doit avoir un visuel et une collision.

## À faire

- [ ] Dans `Main.tscn`, sous `World`, ajouter un node `Platform` de type `StaticBody2D`.
- [ ] Ajouter un enfant `CollisionShape2D`.
- [ ] Utiliser une forme `RectangleShape2D`.
- [ ] Régler la taille de la collision, par exemple largeur 900 px, hauteur 40 px.
- [ ] Placer la plateforme vers le bas de l'écran.
- [ ] Ajouter un visuel simple : `ColorRect`, `Sprite2D` ou `Polygon2D`.
- [ ] Vérifier que le sol est visible.

Structure possible :

```text
World (Node2D)
└── Platform (StaticBody2D)
    ├── CollisionShape2D
    └── Visual
```

## Critères de validation

- [ ] La plateforme est visible.
- [ ] La plateforme possède une collision.
- [ ] La plateforme est placée en bas de l'écran.
- [ ] Le projet se lance sans erreur.

## Commit attendu

```text
Add static platform
```
