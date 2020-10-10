# TD 1
## Remarques préliminaires
* Pour l'ensemble des TDs, vous créerez un compte individuel sur [github](https://github.com/).
Vous nommerez ce compte de la façon suivante: `uvsq<MonNuméroÉtudiant>`.
Par exemple, pour un étudiant de numéro *21601234*, le compte sera `uvsq21601234`.
* Les commandes `git` sont à taper en ligne de commande dans un *shell*.
* Vous pouvez utiliser l'IDE de votre choix.
Sur le cartable numérique, [Eclipse](www.eclipse.org), [IntelliJ IDEA](http://www.jetbrains.com/idea/) et [Visual Studio Code](https://code.visualstudio.com/) sont installés.
* Vous répondrez aux questions directement dans ce fichier en complétant les emplacements correspondants
* Vous déposerez une archive contenant l'ensemble de votre travail sur Moodle.

## Partie en présentiel : découverte de `git`
Dans cet exercice, vous créerez une classe `Fraction` représentant un nombre rationnel et une classe `Main` qui testera les méthodes de la classe `Fraction` **avec des assertions**.
À chaque étape, consultez le statut des fichiers du projet ainsi que l'historique.

1. Sur la forge, créez le projet Java `SimpleFraction`;
En terme de *commits*, quelle différence constatez-vous entre cocher une (ou plusieurs) des cases *Initialize this repository with* et n'en cocher aucune ?
   
 > Le depot contiens deja des élements si on coche les cases, sinon il est vide.
   
    Pour la suite, ne cochez aucune de ces cases.
1. Localement, configurez `git` avec votre nom (`user.name`) et votre email (`user.email`);
    ```bash
    git config --global user.name "Amir HAMMAD"
    git config --global user.email amir.hammad@ens.uvsq.fr
    ```
1. Initialisez le dépôt `git` local pour le projet;
    ```bash
    mkdir TD1
    cd TD1
    git init
    git remote add origin https://github.com/uvsq21605073/SimpleFraction.git
    git pull origin master
    ```
1. Créez la classe `Fraction` (vide pour le moment) et la classe `Main` (avec un simple affichage) dans le projet;
Vérifiez que le projet compile et s'exécute dans l'IDE;
Validez les changements;
   
    ```bash
    # Commandes pour valider les changements
    Sur Eclipse, Run main (le bouton vert) ou
    javac fraction.java
    javac main.java
    java main
    ```
1. Ajoutez un constructeur et la méthode `toString` à la classe `Fraction` et modifiez la classe `Main` en conséquence;
Validez les changements;
   
    ```Java
    // Code pour tester toString
    Fraction F = new Fraction("Hello World");
    System.out.print(F.toString());
    ```
1. Publiez vos modifications sur le dépôt distant;
Vous utiliserez le protocole `https` pour cela;
Vérifiez avec le navigateur;
   
    ```bash
    # Commandes pour publier les modifications
    git add .
    git commit -m "message"
    git push origin master
    ```
1. Sur la forge, ajoutez un fichier de documentation `README.md`.
Quelle syntaxe est utilisée pour ce fichier ?
   
    > Add file > Creat new file > README.md
1. Récupérez localement les modifications effectuées sur la forge.
    ```bash
    mkdir new file
    cd new file
    git init
    git remote add origin https://github.com/uvsq21605073/SimpleFraction.git
    git pull origin master
    ```
1. Ajoutez les répertoires et fichiers issus de la compilation aux fichiers ignorés par `git` (fichier `.gitignore`);
    ```bash
    # Copier ici le contenu de `.gitignore`
    /bin/
    ```
1. Retirez les fichiers de configuration de l'IDE du projet;
    ```bash
    # Répondre ici
    ```
    Ajoutez-les aux fichiers ignorés par `git`.
    ```bash
    # Copier ici les modifications de `.gitignore`
    
    # Compiled class file
    *.class
    
    # Log file
    *.log
    
    # BlueJ files
    *.ctxt
    
    # Mobile Tools for Java (J2ME)
    .mtj.tmp/
    
    # Package Files #
    *.jar
    *.war
    *.nar
    *.ear
    *.zip
    *.tar.gz
    *.rar
    ```
1. Configurez l'accès par clé publique/clé privée à la forge (cf. [Use the SSH protocol with Bitbucket Cloud](https://confluence.atlassian.com/bitbucket/use-the-ssh-protocol-with-bitbucket-cloud-221449711.html)).
    
    > Expliquez la procédure de façon synthétique

## Partie en distanciel : révisions et perfectionnement *shell* et *IDE*
### Maîtriser le *shell* de commandes
L'objectif de cet exercice est de vous faire réviser/découvrir les commandes de base du *shell* de votre machine.
Vous pouvez répondre en utilisant le shell de votre choix (*bash*, *Powershell*, ...).
Pour répondre à ces questions, vous devez effectuer les recherches documentaires adéquates (livre, web, ...).

1. Quel OS et quel shell de commande utilisez-vous ?
    
    > Ubuntu 16.04 ainsi le shell d'ubuntu par default
1. Quelle commande permet d'obtenir de l'aide ?
Donnez un exemple.
   
    ```bash
   man pour l'utilisation du manuel ou help
    ```
1. Donnez la ou les commandes shell permettant de
    1. afficher les fichiers d'un répertoire triés par taille (taille affichée lisiblement)
        ```bash
        ls -s
        ```
    1. compter le nombre de ligne d'un fichier
        ```bash
        wc fichier
        ```
    1. afficher les lignes du fichier `Main.java` contenant la chaîne `uneVariable`
        ```bash
        grep "chaine" README.md -n
        ```
    1. afficher récursivement les fichiers `.java` contenant la chaîne `uneVariable`
        ```bash
        grep "chaine" *.md -n
        ```
    1. trouver les fichiers (pas les répertoires) nommés `README.md` dans une arborescence de répertoires
        ```bash
        find . -name README.md
        ```
    1. afficher les différences entre deux fichiers textes
        ```bash
        diff -y fichier1 fichier2
        ```
1. Expliquez en une ou deux phrases le rôle de ces commandes et dans quel contexte elles peuvent être utiles pour un développeur.
    * `ssh`
        
        > Il permet de transférer des fichiers de facon securisé vers un serveur ou une machine distante.
    * `screen`/`tmux`
        
        > Screen et Tmux  permettent d'ouvrir plusieurs terminaux dans une même console
    * `curl`/[HTTPie](https://httpie.org/)
        
        > Curl et HTTPie  sont des clients HTTP en ligne de commande et  sont utilisés pour tester, déboguer et généralement interagir avec les serveurs HTTP.
    * [jq](https://stedolan.github.io/jq/)
        
        > Un programme jq est un "filtre", il prend une entrée est produit une sortie. Il possède beaucoup de filtres intégrés pour extraire un champ particulier d’un objet, ou convertir un nombre en une chaîne, ou d’autres tâches standard.

### Découverte de votre *IDE*
Dans cet exercice, vous expliquerez en quelques phrases comment vous réalisez les actions ci-dessous dans votre IDE.
Vous pouvez choisir l'IDE/éditeur de texte de votre choix.
Pour réaliser cette exercice, vous devez bien évidemment vous reporter à la documentations de l'IDE ([IntelliJ IDEA](https://www.jetbrains.com/help/idea/discover-intellij-idea.html#developer-tools), [Visual Studio Code](https://code.visualstudio.com/docs), [Eclipse](https://help.eclipse.org/2020-09/index.jsp), ...).

1. Quels IDE ou éditeurs de texte utilisez-vous pour le développement Java ?
    > Eclipse

    Pour la suite, ne considérez que l'un de vos choix.
1. Comment vérifier/définir que l'encodage utilisé est *UTF-8* ?
    
    > Window > Préférences, menu General > Workspace et modifier dans l'écran l'encodage,  UTF-8
1. Comment choisir le JDK à utiliser dans un projet ?
    
    > Java > Compiler, et dans "Compiler compliance level" selectionnez le JDK voulu
1. Comment préciser la version Java des sources dans un projet ?
    
    > Pour préciser une version de java, il faut cocher « Utiliser une compatibilité propre au projet » et de sélectionner la version à utiliser dans la liste déroulante.
    >
    > Il est possible de modifier la version du JDK à utiliser dans les préférences du projet.
1. Comment ajouter une bibliothèque externe dans un projet ?
    
    > telecharger une bibliotheque sur votre pc et au haut de la page java ecrire import.nomdupackage
1. Comment reformater un fichier source Java ?
    
    > Cliquez avec le bouton droit sur la racine du projet et sélectionnez Source -> Format.
1. Comment trouver la déclaration d'une variable ou méthode ?
    
    > Ctrl + F et ecrire la déclaration d'une variable ou méthode à trouver.
    >
    > ou Ctrl + Shift + R
1. Comment insérer un bloc de code prédéfini (*snippet*) ?
    
    > copier coller le code
1. Comment renommer une classe dans l'ensemble du projet ?
    
    > Selectionner la **classe** dans la vue « Packages » ou positionner le curseur sur la définition du nom de la **classe** dans l'éditeur. Puis il faut utiliser l'option « **Renommer** » du menu contextuel « Propager les modifications ».
1. Comment exécuter le programme en lui passant un paramètre en ligne de commande ?
    
    > Dans le shell, aller au repertoire du main et compiler et executer manuellement.
1. Comment déboguer le programme en visualisant le contenu d'une ou plusieurs variables ?
    
    > Sur le coté gauche de la ligne de l'erreur, une icone avec un croix propose en cliquant dessus plusieurs modification possible afin de deboguer le programme.
1. Quels paramètres ou fonctionnalités vous semblent particulièrement importants/utiles pour le développement Java ?
    
    Le debogage.
