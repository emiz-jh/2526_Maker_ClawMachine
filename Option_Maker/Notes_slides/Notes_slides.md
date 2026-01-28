# **Jeu 15/01**

* Rétro-planning = Diagramme de Gantt
* Tout faire sur GitHub :
    * Faire un tuto de notre projet en markdown (README)
    * Pas de drive
    * Mettre tous les livrables dessus
    * Mettre au fur et à mesure notre évolution
* Site Maker
* Doc de commande comme en projet de 2A
* 1 cours = 1 projet = 1 livrable = 1 évaluation

## **LIVRABLES**
* **1 cours = 1 projet sur maker.ensea.fr = 1 livrable**
* Github = code source avec versionning
* Rapport : une personne habituée des fablab doit pouvoir reprendre facilement votre projet et le réaliser (github)
    * A créer des aujourd’hui,
    * A mettre en public,
    * Le nom du github : "2526_Maker_XXX",
    * Hiérarchiser vos fichiers,
    * Le README
* Github avec code source
* Video courte format Insta (<90 sec)

* **!! Dépot des livrables sur le site Maker !!**

    * MC = Macro Compétence
    * Juste screeenshot de la photo peut suffire (notamment CAO),  pas besoin d'un long texte
    * 100% partout quasi-impossible, 60-70% c'est déjà assez dur
    * Mini-projet en plus peut aider pour la note

## **GitHub**

* ssh-keygen -t < ed25519 > -C "< email >"
* clip copie résultat de la commande dans le clipboard

---

# **Lun 19/01**

* Conception Assistée par Ordinateur (CAO)
* Jpeg = pixels
* Vecteur = courbes, zoomable à l'infini sans perte de qualité

# **Jeu 22/01**

* **Imprimantes 3D récentes**
    * Bed (le coeur)  = axe Z, hotend (corps XY) = axe X et Y
    * Extruder pousse le filament
    * Nozzle = ensemble qui chauffe

* **Problèmes possible d'impression**
    * Buse bouché = on est obligé de change la tête (200€ chez BambuLab)
    * Choc thermique, pas assez de filament = filament a le temps de refroidir avant de recharger en filament
    * Perte d'adhésion

* **Réduire temps impression** 
    * Réduire distance à parcourir pour la tête en changeant les paramètres ou en changeant l'épaisseur d'une tranche 
    * Gagner en vitesse d'impression en accélérant la vitesse du buse 

* **Bonnes pratiques quand on veut faire plusieurs pièces**
    * pas tout mettre sur la même imprimante
        * très long (car couche par couche) et la tête passe son temps à se déplacer
        * si ça plante, ça plante toutes les pièces en même temps

* **PLA**
    * un des seul risque est de mettre ses doigts sur la buse

* **Règle de design** 
    * Jeux de 0.2/0.3 minimum pour faire coulisser les pièces
    * Pièce avec un angle de 30° : ça s'imprimera encore à peu près correctement
    * Bridge : dans le vide avec support des 2 côtés
    * Epaisseur de 2 mm ça passe encore

    * il est possible de casser dans le sens des couches
        * ex : on a une tige imprimé sur la hauteur = facile à casser en 2 ; imprimé en longueur = plus difficile à casser

    * Infill = remplissage
    * au dessus de 30/40% : la pièce est déjà très résistant, ça permet de gagner du temps d'impression et éviter de gaspiller du filament

    * Les têtes d'impression se calibrent automatiquement de nos jours

* **Adhésion : solutions**
    * Skirt : tester si filament est bien chauffé, ne touche pas la pièceà imprimer
    * Brim : évite qu'un coin se lève
    * Raft : en général, on n'aura pas besoin d'aller jusque là en projet

* **Pour aller plus loin**
    * Post processing : on taille/lisse après impression
    * Plating : mettre une couche de métal en plongeant pièce dans un bain de métal pour rendre la pièce conductrice (ex : pour faire une antenne)

* **STL**
    * = suite de petits segments (slide 38 : le cercle rouge c'est ce qu'on va obtenir)
    * peut être écrit en ASCII ou en binaire (réels de 32 bites (4 bytes); plus compacte que le ASCII)
    * STL traduit en gCode ensuite : je travaille en millimètres, j'éteins le ventilo, bouge la tête à une coord de tel millimètre de haut etc...

* **Slicing**
    * Logiciel permettant de traduit STL en gCode, varie selon les marques des imprimantes
    * Utiliser les slicers propriétaires des imprimantes uilisées

## **Filaments** 
* **PLA = matière basique**
  * très facile à imprimer
  * basse température*
  * biodégradable (fait en partie d'amidon de maîs) 
  * bcp de couleurs dispo
  * faire attention à la déformation due à la chaleur (pour les cartes éléctroniques par ex)
  * coûte relativement pas cher
* **ABS**
  * très résistant
  * pb d'accroche entre-couche et mauvaise adhésion, fumées toxiques et odeurs
  * c'est cool pour les systèmes mécaniques 
* **PETG**
  * bouteille de coca
  * matière résistance
  * pas trop d'émanation de chaleur/ de gaz
  * Facilité d'impression proche du PLA 
  * possible d'imprimer des matières transparentes de couleur

* **TPU**
  * matière flexible (ex : cahouchouc)
  * Bowden : syst où on envoie filament vers un moteur qui contrôle tête d'impression
  * pas possible de poncer (avec du sable par ex), impression lentes pour des pb mécaniques pour avoir impression de qualité
  * différents Shore et couleurs dispo 
      * Shore A en dessous de 60 impossible à imprimer, il faut minimum 75
      * Classique : Shore A 88, Shore A 95, Shore A 98

* **ASA**
  * proche des propriétés de l'ABS (un peu plus facile à impremer que l'ABS)
  * résiste à UV, température et humidité : matière parfaite pour être à l'extérieur

* **Nylon**
  * très bon coeff de glissement : pratique pour les pièces qui coulissent
  * plutôt simple à imprimer, mais à tendance à absorber l'humidité qui peut pourrir à l'intérieur de la machine (le filament peut buller/brûler (?)), nécessite donc séchage
  * la pièce imprimée continue à prendre l'humidité 

* **PLA / PETG / ASA Chargé en Carbone/Verre/Métal**
  * PLA CC30 : PLA chargé carbone à 30%
  * Abrasif (buse inox/acier trempé)

* **PVA**
  * Soluble dans l'eau chaude
  * Eviter environnement humide

* **Composite**
  * Déposer de la matière chargée très fortement pour avoir une pièce, puis post traitement où il faut dissoudre 20% de la pièce par ex pour garder la partie métalique/ céramique, et on se retrouve avec 80% de pur métal/céramique
  * Très compliqué à imprimer, réglages complexes
  
### Export fichier SL

* Mettre résolution fine

### Slicer

* 0.2
* foces > nb de murs = 2
* top surface = mono line
* densité 15%
* gyroïd = pattern avec les vagues
* speed : garder les spped par défaut
* PLA pas aller au dessus de 200-300 mms
* Brim = augmente adhésion
  
# **Lun 26/01**

## **Découpeuse Laser au FabLab** 
* On a une découpe CO2 au Fablab
* Découpage du bois (MDF) et acrylique possible
* Forte odeur de barbecue pendant qq jours
* Très rapide (qq minutes pour le laser vs qq heure pour l'impression 3D)
* Acrylique plus rigide mais plus cassant, peut servir pour faire des engrenages
* Gravures possibles à l'ENSEA
* Eviter PVC : toxique et corrosif pour l'humain et la machine
* Eviter aluminium brut
* Utiliser des matériaux plat et lisse
  
# Tuto

* Create Drawing
* Custom template
* Do not include > Do not include
* ISO > A2 > mm > Comma > ISO > No Views
