1. L'identifiant court du premier commit est : 4e89d38
2. Le commit correspondant à l'ajout de la page Contact est : 89d5c6b (ou 35bc686 pour la fin)
3. Le nombre actuel de commits est : 6
4. La commande utilisée pour afficher l'historique sous forme graphique est : git log --oneline --graph --all
5. La commande pour examiner précisément le commit de la page Contact est : git show 35bc686


Mission 8 :
J'ai utilisé la commande `git reset --soft HEAD~1`. 
Les modifications sont toujours présentes car l'option `--soft`  annule le commit mais conserve les changements dans le fichier de travail. 
La méthode qui aurait supprimé les modifications du fichier en plus d'annuler le commit est `git reset --hard HEAD~1`.

Mission 9 :
J'ai utilisé la commande `git revert`. La méthode est différente de la mission 8 car `revert` crée un nouveau commit qui annule les modifications, au lieu d'effacer le commit de l'historique. C'est indispensable pour un commit déjà partagé afin de ne pas perturber le dépôt distant des autres développeurs.

Mission 11 :
J'ai utilisé la commande `git cherry-pick 15e52bc`. L'identifiant du commit récupéré est 15e52bc. 
Une fusion classique n'était pas adaptée car la branche contenait d'autres commits expérimentaux que je ne voulais pas intégrer à la branche principale.


Mission 12 :
Dans la version 1.0.0, les trois nombres représentent:
- 1 : Version Majeure (changements majeurs ou refonte incompatible).
- 0 : Version Mineure (ajout de nouvelles fonctionnalités rétrocompatibles).
- 0 : Patch / Correctif (correction de bugs mineurs).

Les versions suivantes seraient :
- Pour une correction de bug mineur : v1.0.1
- Pour une nouvelle fonctionnalité compatible : v1.1.0
- Pour une refonte majeure incompatible : v2.0.0



### Questions finales

1. **Différence entre les zones** : La zone de travail contient les fichiers modifiés localement. La zone de staging est l'espace où l'on prépare le prochain commit. L'historique contient les versions définitivement enregistrées.
2. **Branche dédiée** : Cela permet de travailler sur une fonctionnalité de manière isolée sans risquer de casser la branche principale (`main`), et de faciliter le travail collaboratif.
3. **Différence d'annulation** : `reset` (mission 8) modifie l'historique en effaçant le commit, idéal pour du local. `revert` (mission 9) crée un nouveau commit qui annule les effets du précédent, ce qui est obligatoire pour ne pas casser l'historique d'un dépôt partagé.
4. **Utilité du stash** : Il sert à mettre temporairement de côté des modifications non terminées pour changer de branche en urgence, sans avoir à faire un commit incomplet.
5. **Cherry-pick vs Merge** : Récupérer un commit précis permet de n'importer qu'une seule correction spécifique, sans ramener tout le code expérimental ou non terminé d'une autre branche.
6. **Rôle de HEAD** : HEAD est un pointeur qui indique la position actuelle de Git (sur quel commit ou quelle branche on se trouve actuellement).
7. **HEAD~2** : Cela représente le commit situé deux crans avant la position actuelle de HEAD.
8. **Utilité d'un tag** : Un tag permet de marquer un point précis dans l'historique (comme une release ou une version stable v1.0.0) pour le retrouver facilement.
9. **Commits petits et précis** : Ils permettent de comprendre facilement l'évolution du projet, et rendent les opérations comme `revert` ou `cherry-pick` beaucoup plus simples et ciblées.
10. **Fichiers à ne pas versionner** : Il ne faut pas versionner les fichiers contenant des données sensibles (mots de passe, API keys dans `.env`), les fichiers temporaires/logs qui changent tout le temps, ou les gros dossiers générés automatiquement (comme `node_modules` ou `cache`).