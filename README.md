# PCB_TravailleurIsole

# Présentation du projet :

Le projet consiste à fabriquer un badge pour les travailleurs isolés.

Celui-ci a pour but de détecter si le travailleur qui le porte fait un malaise et enverrait un signal d'alarme ainsi que la position du travailleur à l'accueil pour qu'ils puissent prévenir les secours.

Pour ce faire, on aura besoin d'un capteur d'accélération, d'un GPS et d'un LoRaWan pour envoyer les alertes.

On établit une accélération seuil selon x,y,z. Si la valeur donnée par le capteur dépasse ce seuil, on considère que le travailleur a chuté : un premier signal est envoyé à l'utilisateur. Concrètement : une LED s'allume sur le badge. L'utilisateur a alors une durée ts de quelques secondes pour appuyer sur le bouton "fausse alerte" s'il a juste trébuché ou s'il n'est pas en danger. Ce bouton va alors réinitialiser le programme et aucune alerte ne sera envoyée à l'accueil.
Si au bout de ts l'utilisateur n'a pas appuyé sur le bouton de fausse alerte, on considère que le travailleur est en danger : le badge envoie donc grâce au LoRaWan la position donnée par le GPS ainsi qu'un message d'alarme à l'accueil. Le personnel présent pourra alors prévenir les secours pour lui venir en aide.

# Lien des différentes parties du projet :
Lien ressources LoRaWan :https://github.com/OliverBELLIARD/LoRaWAN.

Lien ressources batterie :https://github.com/inassra/batterie.

Lien ressources accéléromètre et GPS :

# Elements à ajouter au projet :

Ajouter un buzzer qui fait du bruit quand la première alerte est envoyée pour que le travailleur s'en rende compte et puisse appuyer sur le bouton si c'est une fausse alerte.

Ajouter un deuxième bouton afin que le travailleur puisse prévenir lui même s'il ne se sent pas bien.

Valeur seuil de l'accélération complètement à revoir, notre projet était surtout basé sur la conception du PCB et faire le code pour le LoRaWan, l'accéléromètre et le GPS donc on a mit une valeur en ordre de grandeur sans trop s'y attarder. Peut être que modifier le code pour prendre la vitesse (en dérivant) au lieu de l'accélération serait une bonne piste à explorer. Prendre en compte la position selon l'axe z et étudier des différences de potentiels est aussi une idée que l'on souhaitait développer. En effet lors d'un malaise la variation de vitesse n'est pas si grande (la chute ne dure qu'1m pour le capteur) et l'accélération seuil peut se confondre avec l'accélération d'un travailleur qui passe d'une vitesse nulle à une vitesse de marche(~7km/h) ou à une vitesse de course (~12 km/h)

Notre accélération finale est la norme des accélérations selon les axes x, y et z. Ne considérer que l'accélération selon z peut aussi être envisagé.

Pour le schéma et le board du PCB, ne pas oublier de rajouter un via permettant de relier les plans de masse du dessus et du dessous du PCB. Si ce n'est pas fait les régulateurs vont sauter à cause du microprocesseur qui ne recevra pas la bonne tension.

# Ce que nous a apporté le projet :

Pendant ce projet, nous avons appris à souder, déssouder (lors des erreurs), créer un PCB complexes et les erreurs pouvants etre faites.
Nous avons aussi appris à travailler avec des personnes qu'on ne connassait pas. En tant qu'intégrateur, nous devions donner des deadlines, prendre connaissance des avancements dans chacune des équipes, mettre en connexion ces équipes et les aider si necessaire.
