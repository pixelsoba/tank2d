# Ticket 06 — Ajouter une caméra fixe

## Objectif

Ajouter une caméra fixe qui cadre toute la scène.

## Contexte

Pour ce prototype, la caméra ne suit pas le tank. Elle reste fixe pour voir la plateforme, la cible et les tirs.

## À faire

- [ ] Dans `Main.tscn`, ajouter un node `Camera2D`.
- [ ] Le placer pour cadrer la plateforme.
- [ ] Activer la caméra courante.
- [ ] Tester le lancement du jeu.
- [ ] Ajuster le zoom si nécessaire.

Structure possible :

```text
Main (Node2D)
├── Camera2D
├── World
├── Projectiles
└── UI
```

## Critères de validation

- [ ] Une `Camera2D` existe.
- [ ] La caméra est active.
- [ ] La plateforme et le tank sont visibles au lancement.
- [ ] La caméra ne bouge pas.
- [ ] Le projet se lance sans erreur.

## Commit attendu

```text
Add fixed camera
```
