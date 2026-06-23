# Ticket 01 — Créer la scène principale

## Objectif

Créer la scène principale du prototype.

## Contexte

La scène principale contiendra la caméra fixe, la plateforme, le tank, les projectiles, la cible et l'UI.

## À faire

- [x] Créer une scène `Main.tscn`.
- [x] Sauvegarder la scène dans `scenes/`.
- [x] Utiliser un node racine de type `Node2D`.
- [x] Renommer le node racine en `Main`.
- [x] Ajouter un node `World` de type `Node2D`.
- [x] Ajouter un node `Projectiles` de type `Node2D`.
- [x] Ajouter un node `UI` de type `CanvasLayer`.
- [x] Configurer `Main.tscn` comme scène principale du projet.
- [x] Lancer le projet.

Structure attendue :

```text
Main (Node2D)
├── World (Node2D)
├── Projectiles (Node2D)
└── UI (CanvasLayer)
```

## Critères de validation

- [x] `scenes/Main.tscn` existe.
- [x] `Main.tscn` est la scène principale.
- [x] La structure de nodes est conforme.
- [x] Le projet se lance sans erreur.

## Commit attendu

```text
Add main scene
```
