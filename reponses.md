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