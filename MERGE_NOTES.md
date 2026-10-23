## Fast-forward vs stratégie ort

**Fast-forward**
- Pas une stratégie : c'est un cas particulier où git n'a rien à fusionner.
- Condition : la branche courante n'a pas de nouveaux commits depuis la création de l'autre branche.
- Git déplace juste le pointeur de branche, aucun commit de merge.
- Forcer / interdire :  / .

**ort** (Ostensibly Recursive's Twin)
- Stratégie de merge par défaut depuis Git 2.34 (remplace ).
- Utilisée quand les branches ont divergé : fusion à 3 points (ancêtre commun + les 2 pointes).
- Crée un commit de merge à 2 parents, gère les renommages, résout automatiquement ce qui ne se chevauche pas.
- Plus rapide et plus fiable que .
- Choisir explicitement : .

**Ordre de décision de git** : fast-forward possible ? oui → fast-forward. Non → stratégie (ort) → merge commit.

Merge 2 branch qui modifient la même ligne : 
Il faut aller dans la ligne qui pose problème
Git affiche les deux versions dans les deux branches
Il faut choisir une version et effacer l'autre
Il faut aussi effacer les markers.
Puis vérfier avec "grep -n "<<<<<<<\|=======\|>>>>>>>" NOM_FICHIER" 