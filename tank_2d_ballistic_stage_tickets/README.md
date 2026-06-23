# Tank 2D Ballistic Prototype

Prototype Godot 2D en vue de côté.

Le but est de créer une base simple de mini-simulation balistique :

- caméra fixe ;
- une plateforme unique ;
- un tank joueur ;
- déplacement gauche/droite avec `CharacterBody2D` ;
- visée verticale avec le canon ;
- charge du tir avec la barre espace ;
- projectile balistique simple ;
- cible statique à toucher.

## Contrôles prévus

- Flèche gauche / A / Q : déplacer le tank à gauche.
- Flèche droite / D : déplacer le tank à droite.
- Flèche haut / W / Z : lever le canon.
- Flèche bas / S : baisser le canon.
- Espace maintenu : charger le tir.
- Espace relâché : tirer.

## Objectifs pédagogiques

- Créer un projet Godot 4 en 2D.
- Utiliser `CharacterBody2D` et `move_and_slide()`.
- Comprendre `velocity`.
- Utiliser `delta` pour un déplacement stable.
- Manipuler un angle de tir.
- Convertir un angle en vecteur de direction.
- Simuler une trajectoire balistique simple.
- Créer une UI minimale avec `ProgressBar`.
- Instancier dynamiquement un projectile.
- Détecter un impact sur une cible.

## Structure recommandée

```text
tank-2d-ballistic-prototype/
  README.md
  ROADMAP.md
  docs/
  tickets/
  scenes/
  scripts/
  assets/
    icons/
    reference/
```

## Définition de terminé

Un ticket est terminé seulement si :

- le projet se lance sans erreur ;
- la fonctionnalité demandée est testable ;
- le code est lisible ;
- un commit Git clair a été fait ;
- le résultat peut être démontré rapidement.
