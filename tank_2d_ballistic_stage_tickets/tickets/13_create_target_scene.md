# Ticket 13 — Créer une scène Target

## Objectif

Créer une cible statique que le joueur devra toucher.

## Contexte

La cible donne un objectif au prototype.

## À faire

- [ ] Créer une scène `Target.tscn`.
- [ ] Sauvegarder la scène dans `scenes/`.
- [ ] Utiliser un node racine de type `Area2D`.
- [ ] Renommer le node racine en `Target`.
- [ ] Ajouter un enfant `CollisionShape2D`.
- [ ] Utiliser une forme simple : rectangle ou cercle.
- [ ] Ajouter un visuel `Visual`.
- [ ] Créer un script `scripts/target.gd`.
- [ ] Attacher le script à `Target`.
- [ ] Ajouter une instance de `Target.tscn` dans `Main.tscn`.

Structure attendue :

```text
Target (Area2D)
├── CollisionShape2D
└── Visual
```

## Critères de validation

- [ ] `scenes/Target.tscn` existe.
- [ ] Le node racine est un `Area2D`.
- [ ] La cible est visible dans la scène principale.
- [ ] La cible possède une collision.
- [ ] Le projet se lance sans erreur.

## Commit attendu

```text
Add target scene
```
