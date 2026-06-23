# Ticket 06 — Ajouter une caméra fixe

## Objectif

Ajouter une caméra fixe qui cadre toute la scène.

## Contexte

Pour ce prototype, la caméra ne suit pas le tank. Elle reste fixe pour voir la plateforme, la cible et les tirs.

## À faire

- [x] Dans `Main.tscn`, ajouter un node `Camera2D`.
- [x] Le placer pour cadrer la plateforme.
- [x] Activer la caméra courante.
- [x] Tester le lancement du jeu.
- [x] Ajuster le zoom si nécessaire.

Structure possible :

```text
Main (Node2D)
├── Camera2D
├── World
├── Projectiles
└── UI
```

## Critères de validation

- [x] Une `Camera2D` existe.
- [x] La caméra est active.
- [x] La plateforme et le tank sont visibles au lancement.
- [x] La caméra ne bouge pas.
- [x] Le projet se lance sans erreur.
## Commit attendu

```text
Add fixed camera
```
