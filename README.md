Script de configuration post-installation pour les serveurs Centos 7

(c) Niki Kovacs, 2020
Traduction Robin MILLION

Ce dépôt offre un script "automagique" de configuration post-installation pour les serveurs tournant sous Centos 7 mais aussi une collection de scripts d'aide et des modèles de fichiers de configuration pour les services courants.

En un mot
Réaliser les étapes suivantes :


Installez un système Centos 7 minimal

Créez un utilisateur non root avec les privilèges d'administrateurs

Installez Git : sudo yum install git

Récupérez le script : git clone https://gitlab.com/kikinovak/centos-7.git

Allez dans le nouveau répertoire : cd centos-7

Lancez le scipr : sudo ./centos-setup.sh --setup

Allez prendre un café pendant que le script tourne

Redémarrez la machine

La transformation d'une installation CentOS minimale en un serveur fonctionnel se résume toujours à une série d'opérations plus ou moins longues. Chacun a sa propre manière bien sûr, mais voici ce que je fais habituellement sur une frache installation CentOS :

    Personnaliser le shell Bash : prompt, alias, etc

    Personnaliser l'éditeur Vim

    Configuration des dépôts officiels et tiers

    Installer un ensemble complet d'outils de ligne de commande

    Supprimer un florilège de paquets inutiles

    Permettre à l'utilisateur administrateur d'accéder au système de journaux
    
    Désactiver l'IPv6 et reconfigurer certains services en adéquation

    Configurer un mot de passe persistant pour sudo

    Etc.

Le script centos-setup.sh effectue toutes ces opérations.

Configurez Bash et Vim et définissez une résolution plus lisible de la console :

# ./centos-setup.sh --shell

Configurer les dépôts officiels et les dépôts de tiers :

# ./centos-setup.sh --repos

Installez les groupes de paquets Core et Base avec quelques outils supplémentaires :

# ./centos-setup.sh --extra

Retirez un florilège de paquets inutiles :

# ./centos-setup.sh --prune

Permettre à l'utilisateur administrateur d'accéder au système de journaux :

# ./centos-setup.sh --logs

Désactivez l'IPv6 et reconfigurez les services de base en adéquation :

# ./centos-setup.sh --ipv4

Configurez la persistance du mot de passe pour sudo :

# ./centos-setup.sh --sudo

Réalisez tout cela en une seule commande :

# ./centos-setup.sh --setup

Supprimez les paquets et revenez à un système de base amélioré :

# ./centos-setup.sh --strip

Afficher le message d'aide :

# ./centos-setup.sh --help

Si vous voulez savoir ce qui se passe exactement sous le capot, ouvrez un deuxième terminal et de consulter les journaux :

$ tail -f /tmp/centos-setup.log
