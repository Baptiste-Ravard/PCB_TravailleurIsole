# PCB_TravailleurIsole


Notes sur ce qui n'allait pas, ce qu'il restait à voir :

Ajouter un buzzer qui fait du bruit quand la première alerte est envoyée pour que le travailleur s'en rende compte et puisse appuyer sur le bouton si c'est une fausse alerte.

Valeur seuil de l'accélération complètement à revoir, notre projet était surtout basé sur la conception du PCB et faire le code pour le LoRaWan, l'accéléromètre et le GPS donc on a mit une valeur en ordre de grandeur sans trop s'y attarder. Peut être que modifier le code pour prendre la vitesse (en dérivant) au lieu de l'accélération serait une bonne piste à explorer. Prendre en compte la position selon l'axe z et étudier des différences de potentiels est aussi une idée que l'on souhaitait développer. En effet lors d'un malaise la variation de vitesse n'est pas si grande (la chute ne dure qu'1m pour le capteur) et l'accélération seuil peut se confondre avec l'accélération d'un travailleur qui passe d'une vitesse nulle à une vitesse de marche(~7km/h) ou à une vitesse de course (~12 km/h)

Notre accélération finale est la norme des accélérations selon les axes x, y et z. Ne considérer que l'accélération selon z peut aussi être envisagé.
