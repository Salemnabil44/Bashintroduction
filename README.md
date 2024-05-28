# Bashintroduction

## Étapes du script create-project.sh

- #### Définir le dossier de base
La variable BASE_DIR spécifie le répertoire où les projets seront créés.
Cela permet de modifier facilement l'emplacement du répertoire de projets si nécessaire.

_**Commande**_ : BASE_DIR=~/Projets

- ####Vérification des arguments
Le script vérifie si un nom de projet a été fourni.
Si ce n'est pas le cas, il affiche une erreur et arrête l'exécution.

_**Commande**_ :
if [ -z "$1" ]; then
    echo "Erreur : Aucun nom de projet fourni."
    echo "Usage : $0 <NomDuProjet>"
    exit 1
fi
- #### Récupération du nom du projet

Le nom du projet est récupéré depuis les arguments de la ligne de commande.

_**Commande**_ :
PROJECT_NAME=$1
PROJECT_DIR="$BASE_DIR/$PROJECT_NAME"

- #### Création du dossier du projet

Le script crée un dossier pour le projet dans le répertoire de base spécifié.

_**Commande**_ :
echo "Création du dossier $PROJECT_DIR"
mkdir -p "$PROJECT_DIR"

- #### Initialisation du fichier README.md

Le script crée un fichier README.md dans le dossier du projet.
Il y écrit un titre en markdown comportant le nom du projet.

_**Commande**_
README_FILE="$PROJECT_DIR/README.md"
echo "Initialisation du fichier $README_FILE"
echo "# Projet $PROJECT_NAME" > "$README_FILE"

- #### Initialisation du fichier script .sh

Le script crée un fichier de script .sh portant le nom du projet.
Il y ajoute le shebang #!/bin/bash et lui donne les droits d'exécution.

_**Commande**_
SCRIPT_FILE="$PROJECT_DIR/$PROJECT_NAME.sh"
echo "Initialisation du fichier $SCRIPT_FILE"
echo "#!/bin/bash" > "$SCRIPT_FILE"
chmod +x "$SCRIPT_FILE"

- #### Affichage des messages de confirmation

Le script affiche des messages pour confirmer la création du dossier et des fichiers.

_**Commande**_ : echo "Projet $PROJECT_NAME initialisé"

### Droits d'exécution du script

Pour donner les droits d'exécution au script create-project.sh, utilisez la commande suivante :

_**Commande**_ : chmod +x create-project.sh

Après avoir donné les droits d'exécution au script, vous pouvez l'exécuter comme suit :

_**Commande**_ : ./create-project.sh SuperScript

Cela produira la sortie suivante et créera les fichiers et dossiers correspondants :

Création du dossier /home/nom_utilisateur/Projets/SuperScript

Initialisation du fichier /home/nom_utilisateur/Projets/SuperScript/README.md

Initialisation du fichier /home/nom_utilisateur/Projets/SuperScript/SuperScript.sh

Projet SuperScript initialisé
