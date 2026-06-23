# Ticket 01 — Créer la scène principale

## Objectif

Créer la scène principale du prototype.

## Contexte

La scène principale contiendra la caméra fixe, la plateforme, le tank, les projectiles, la cible et l'UI.

## À faire

- [ ] Créer une scène `Main.tscn`.
- [ ] Sauvegarder la scène dans `scenes/`.
- [ ] Utiliser un node racine de type `Node2D`.
- [ ] Renommer le node racine en `Main`.
- [ ] Ajouter un node `World` de type `Node2D`.
- [ ] Ajouter un node `Projectiles` de type `Node2D`.
- [ ] Ajouter un node `UI` de type `CanvasLayer`.
- [ ] Configurer `Main.tscn` comme scène principale du projet.
- [ ] Lancer le projet.

Structure attendue :

```text
Main (Node2D)
├── World (Node2D)
├── Projectiles (Node2D)
└── UI (CanvasLayer)
```

## Critères de validation

- [ ] `scenes/Main.tscn` existe.
- [ ] `Main.tscn` est la scène principale.
- [ ] La structure de nodes est conforme.
- [ ] Le projet se lance sans erreur.

## Commit attendu

```text
Add main scene
```
