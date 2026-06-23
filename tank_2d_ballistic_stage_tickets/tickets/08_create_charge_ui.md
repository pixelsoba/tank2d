# Ticket 08 — Créer une UI de charge

## Objectif

Créer une barre de charge visible à l'écran.

## Contexte

La barre indiquera la puissance du tir quand le joueur maintient la barre espace.

## À faire

- [ ] Dans `Main.tscn`, sous `UI`, ajouter un `Control` nommé `HUD`.
- [ ] Sous `HUD`, ajouter une `ProgressBar` nommée `ChargeBar`.
- [ ] Régler la valeur minimum à `0`.
- [ ] Régler la valeur maximum à `100`.
- [ ] Régler la valeur initiale à `0`.
- [ ] Placer la barre en bas ou en haut de l'écran.
- [ ] Créer un script `scripts/hud.gd`.
- [ ] Attacher ce script au node `HUD`.
- [ ] Ajouter une fonction `set_charge_ratio(charge_ratio: float)`.

Script possible :

```gdscript
extends Control

@onready var charge_bar: ProgressBar = $ChargeBar

func set_charge_ratio(charge_ratio: float) -> void:
	charge_bar.value = clamp(charge_ratio, 0.0, 1.0) * 100.0
```

## Critères de validation

- [ ] Une barre de charge est visible.
- [ ] La barre commence à 0.
- [ ] Le script `hud.gd` existe.
- [ ] La fonction `set_charge_ratio` existe.
- [ ] Le projet se lance sans erreur.

## Commit attendu

```text
Add shot charge UI
```
