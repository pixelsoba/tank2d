# Ticket 04 — Choisir ou intégrer un visuel de tank

## Objectif

Donner un visuel identifiable au tank.

## Contexte

Le visuel peut venir d'un asset pack ou être provisoire. Le gameplay est prioritaire.

## À faire

- [ ] Choisir un visuel de tank dans l'image de référence ou dans un asset pack.
- [ ] Placer la planche complète dans `assets/reference/` si besoin.
- [ ] Créer ou extraire un visuel simple dans `assets/icons/tank.png` ou `assets/icons/tank.svg`.
- [ ] Assigner le visuel à `BodyVisual`.
- [ ] Ajuster la taille du tank.
- [ ] Vérifier que le centre du tank correspond à peu près à sa collision.
- [ ] Garder un canon séparé si possible.

## Option simple sans extraction

Si l'extraction du sprite prend trop de temps, créer un tank provisoire avec des formes :

```text
BodyVisual : rectangle
BarrelVisual : ligne ou rectangle fin
```

## Critères de validation

- [ ] Le tank est identifiable visuellement.
- [ ] Le visuel est aligné avec la collision.
- [ ] Le canon est visible.
- [ ] Le projet se lance sans erreur.

## Commit attendu

```text
Add tank visual
```
