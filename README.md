# TJ-test-Zerance

Le test a été réalisé sur Shopify à l'aide du themekit et d'un thème vierge généré via ce dernier.
L'ensemble des feuilles de style du thème a été remplacé par des feuilles de style custom.

Pour ce mini-projet j'ai utilisé:

- IDE: Atom (https://atom.io/).
- Grid-css: Simple Grid (https://simplegrid.io/).
- Lecture et extraction des informations de la maquette: Gimp/Photoshop site https://studiozerance.fr/.
- API de validation de genre: https://gender-api.com/fr.

Pour accéder au projet:

- Site: thomasjudic.myshopify.com
- Mot de passe du store: theaff

Pour accéder aux fichiers et aux paramètres configurables du projet:

- Site: https://accounts.shopify.com/store-login
- Boutique: thomasjudic
- Compte: compte d'admin de la boutique.

## Synthèse du projet

J'ai réparti mon temps de travail de façon à travailler sur le test environ 3h30 par jour, les Samedi 10 Avril 2021 et Dimanche 11 Avril 2021.
J'ai subi quelques turbulences en route avec mon propre matériel, ce qui m'a fait perdre environ 1 heure de travail.
Durant la réalisation de ce projet, la notion d'espace temps s'est comme litéralement altérée, donnant l'impression que 5 minutes de temps écoulés dans ma tête étaient en réalité 1 heure 'irl' (Critère de choix selon moi, prouvant mon intérêt certain ce projet).
Dans tous les cas, j'ai taché de jouer selon les règles préconisées dans les instructions du projet, ne pas dépasser les 7 heures de réalisation.
C'est donc un projet hélas inachevé que je réstitue, en toute transparence, dans cette fourchette de temps.

Mon plan de bataille a été le suivant:

## Création de la structure du thème (env 3 Heure)
  ### Arborescence du thème
    J'ai décidé de créer un thème en 5 sections liquid, reprenant respectivement celles demandées dans le cahier des charges, réparties de la manière suivante:
      - Les sections 'bannière' et 'header' dans le Header du thème.
      - Les sections 'portofolio' et 'slider' dans le contenu de page du thème (main)
      - La section 'text_infinite' dans le footer du thème.
    Par la suite, j'ai souhaité faire un thème full css, centralisant les variables dans un fichier distinc, le grid-css dans un autre, et les autres règles dans le dernier.
  ### Images du thème
    J'ai extrait directement les logos clients du site du studio Zerance, pour les convertir ensuite en png, avant de les importer dans le répertoire "assets" du thème.
    Le logo Universal a été extrait du fichier de maquette en prenant les dimensions des images extraites juste avant comme référence.
    L'extraction du trait de soulignage jaune demandé dans le projet a été réalisé via le site également.
    
  ### Ecriture de la base html et des schemas des sections
    Je me suis beaucoup concentré sur les schemas en premier lieu dans cette partie, imaginant comment automatiser au maximum le rendu du contenu configuré via le thème.
    J'ai tout d'abord généré les ébauches des {% schema %} pour ensuite tester leur viabilité syntaxique et les ajuster au besoin.
    Viennent ensuite les structures html, où j'ai implémenté les variables des schema pour ensuite tester leur rendu sur la page du thème.
    Cette partie a sans doute été allongée par les divers essais que j'ai réalisé afin d'obtenir le résultat que j'imaginais, dans un élan sans nul doute perfectionniste de minimiser le contenu statique du code.
    
 ## Modules du thème (env 3 heures)
  ### Le formulaire de contact
    Dans l'idéal, j'aurai souhaité générer conditionnelement le contenu html du formulaire en fonction de son activation ou non via les paramètres du thème.
    Dans un souci de plutôt optimiser le temps imparti par le projet, j'ai implanté ce code de manière statique dans un snippet rendu dans le contenu de page de l'index du thème.
    Le paramétrage de l'activation du formulaire via le thème ne permet donc que d'afficher ce dernier dans le menu de navigation du thème, afin de le rendre accessible à tout utilisateur.
    Concernant la structure du formulaire, j'ai fais dans la sémantique, avec les <fieldset> que j'estimais cohérents, afin de faciliter l'utilisation du grid css plus tard.
  Pour la vérification des valeurs de champs, j'ai ajouté le fameux "required" à chaque balise <input>.
    
   Pour pouvoir tester ce formulaire en conditions réelles, lors de l'élaboration de son module javascript de vérification de genre, je me suis concentré de suite sur sa mise en place dans l'overlay, que j'ai également implanté sur le coup.
   
   Concernant le module de validation de genre, j'ai tout simplement utilisé l'attribut "onsubmit" du formulaire, afin d'obtenir directement la valeur saisie dans l'input du prénom comme variable de fonction, appelée via le fichier javascript dédié où celle-ci a été écrite.
   La fonction de validation en elle-même va donc utiliser la valeur de sa variable afin de, dans des fonctions séparées:
   - générer l'url de requête de l'Api de validation de genre en utilisant des variables globales comme base.
   - appeler une fonction de requête fetch avec l'url générée précemment et attendre le réponse avant de retourner la valeur attendue par cette dernière => Le genre.
   - Utiliser ce genre pour le passer dans une instruction switch, et finalement retourner la réponse appropriée dans une pop-up (La subtilité du "It's a trap" de par sa double référence selon moi habite encore mes pensées à l'heure où j'écris ce compte-rendu).
   - Pour la fermeture du formulaire et de son overlay, j'ai hésité entre utiliser le javascript ou trouver un moyen de jouer avec le css. Hélas je n'ai pu explorer ces pistes faute de temps à ce moment.
   
   
