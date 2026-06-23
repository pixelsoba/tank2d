# Ticket 04 — Choisir ou intégrer un visuel de tank

## Objectif

Donner un visuel identifiable au tank.

## Contexte

Le visuel peut venir d'un asset pack ou être provisoire. Le gameplay est prioritaire.

## À faire

- [x] Choisir un visuel de tank dans l'image de référence ou dans un asset pack.
- [x] Placer la planche complète dans `assets/reference/` si besoin.
- [x] Créer ou extraire un visuel simple dans `assets/icons/tank.png` ou `assets/icons/tank.svg`.
- [x] Assigner le visuel à `BodyVisual`.
- [x] Ajuster la taille du tank.
- [x] Vérifier que le centre du tank correspond à peu près à sa collision.
- [x] Garder un canon séparé si possible.

## Option simple sans extraction

Si l'extraction du sprite prend trop de temps, créer un tank provisoire avec des formes :

```text
BodyVisual : rectangle
BarrelVisual : ligne ou rectangle fin
```

## Critères de validation

- [x] Le tank est identifiable visuellement.
- [x] Le visuel est aligné avec la collision.
- [x] Le canon est visible.
- [x] Le projet se lance sans erreur.

## Commit attendu

```text
Add tank visual
```
