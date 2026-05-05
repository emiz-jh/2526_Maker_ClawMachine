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


# **Jeu 29/01**

* Remplir tous les champs NPN sur Kicad
* Installer le plugin Interactive Html Bom

# Lundi 02/02/26

## I2C
* I2C pour lire il fait arr^ter décrire
* un me=aire et plusieurs esclave
* transistor impose état bas, état haut est par défaut
* 1 résistane de pull-up par ligne et pas par périphérique, résistance variable
* transistor ouvert = condo

## SPI
* I2C et SPi sont synchrone car partagent une horloge
* SPI full-duplex = une ligen dans un sens ou dans l'autre

## USB
* créé pou remplacer l'HUART
* plusieurs norme : high-speed (standard)
* plug & play : ça marche en branchant et on peut débrancher sans pb
* USB = bidirectionel

* USB C a plus de PIN que USB normal (car on peut brancher dans les 2 sens)
* "+ "et des"-" sont des pertes différéntielles
* résistance de 5,1 kohm entre ... et la masse et ... la masse
* ajouter le composant avec 5 diodes pour protéger circuit, limite les tensions entre 0 et 5,1 V
* diode de protection en cas de surcharcge
* à soude rau plus près du connecteur
* pistes proche l'une de l'autre, quasi rien en dessous
* les vaguelettes diapo 11 c'est tuneless pour rallonger les pistes les plus courtes pour qu'elles soient égales aux autres pistes, car très rapides
* fils longs = successions de condo et bobines
* ondulations due au circuit élec => rajouter une résistance en série en amont pour limiter ondulations
* encoder = 2 interrupteurs pour détecter appuis
* condo permet de gérer charge et décharge via la résistance
  
## Diode TVS
* supprime tous les gros pics de décharges (cg Maxie et PPZ qui se prennent des jus pour l'atelier soudure xD)
* dès qu'il y a surplus, le courant passe dans la diode pour éviter de se prendre une chataigne
* filtre LC pour filtrer bruit et mettre condo au plus proche des condo
* en mettre sur chaque connecteur où ill y a du signal

## Datasheet
* applications notes fournis un doc pour nous montrer comment marche un composant compliqué (cf amp audio), sinon pour les petits composnats, tout est dans la datasheet
* schéma = comprendre le circuit
* routage = réalise le circuit, n'est pas le schéma
* VDD = drain, Vss = source
  
## Symbol editor
* quand on a pas le bon composant existant dans Kicad
* ne pas chercher des symboles sur Internet car en général on se retrouve avec une copie de l'emprunte (pin dans l'ordre dans ce cas )=> l'ordre des pins n'est souvent pas dans l'ordre en pratique en général !

### Bonnes pratiques ordres des pins
* créer une nouvelle librairie
* toutes les alims en haut et toutes les masses en bas
* attention, il n'y a souvent pas qu'une suele masse (elles sont cachées le sunes derrières les autres)
* entrées à gauche et sorties à droites

### Electrical type pins 
* input = reçoit un signal qui vient d'une autre
* output = peut être câblé sur plusieurs entrée, pas cablage sur un autre output, génère un signal utilisable par un autre composant
* power_input = pin qui reçoit une alimentation
* Tri-state : on peut imposer 1 ou 0, en haute impédance (connecteur ouvert)
* masse vue comme une alimentation a 0V = power_input

### création librarie 
* cf slide 29
* toujours vérifier si les composants n'existennt pas déjà
* il faut faire des calculs pour que ça corresponde à la réalité
*  définir si c'est composant monté en surface ou traversant
  
### numérotation des PINS
* vérifier top view ou bottom view !!!!!
* composants avec plusieurs sens possibles = rotation dans le sens direct
* pin numéro 1 est donné par rond ou triangle (puis on compte dans les sens direct)
* attention dimention en **millimètre** ou en **millième de pouce** par ex

### Layers dans le footprint editor de KiCad*
* diapo 33
* Mask c'est là où il n'y a pas de verni (pour mettre pâte à braser par ex, laisser les pads des composants traversants) 
* Courtyard = composants trop proches entre eux, KiCad nous insulte
  
## Page hiérarchique
* pour PCB complexe
* processeur = 1 page
* batterie BMS = 1 page
* carte SD = 1 page
* partie analogique = 1 page
* labels globaux = label accessibke par toutes les pages
* label locaux = n'est définie que dans la page
* label hiérarchique = def comme entrée et sorties d'une fonction (losanges, triangle coupé)
* sur la page principale, pour faire apparaitre label hierarchique : clic-droit place sheet pin
* on peut dupliquer par ex 3 composants associée à 3 pages hiérarchiques identiques

## Datasheet et MPN
* définir le MPN, surtout pour les composants spéciifiques (hors résistances ou condos classiques): clic-droit > symbol properties 
* SKU = c'est le numéro du QR code du manufactureur

## Electric Rules Checker
* 0%

## Composants
* déterminer taille PCB et trous de fixations
* un truc avec bcp de pins = placer au centre
* Connecteurs coudés : faire en sorte que les cables partent vers l’extérieur de la carte et pas au-dessus, il y a un sens
* câblé vers nous = Pin 1 est à gauche
* led avec les leds, condo de decouplage ensemble, ...

## 4 couches
* 1 plan de masse et 1 plan d'alim
* puissance à droite, logique à gaucge, puissance intermédiaire (driver) au center
* 1 via = 1 ampère qu'on peut passer
* via dans le pad est possible pour les petits composants
* couche internes sont plus fines que couches externes => on peut passer moins de courant : mettre les plans très large pour pas que ça chauffe

## Stackup - Configuration
* isolant du milieu souvent + épais car c'ets lui qui fait rigidité du PCB
* Board Setup (2eme onglet de la barre de menu du haut)
* PCB en alu bien pour la dissipation thermique, mais comme c'est conducteur, pas de couche bottom possible, droit à qu'une seule couche
* Cooper layer = 4
* ne pas changer In1, In2, ... => renommer la fin avec des "-"
  
## Contraintes
* données par le fabriquant
* 1 oz = 35 microns
* trou de 0.3mm/0.4/pad de 0.45mmm
* blind via = entre 2 couches internes => cher, ne pas faire
* réduire de 10% solder mask pour pate à braser


hub usb 4 ports en sortie : CH334F
pogo pin = pin sur ressort



# Lundi 09/02/26

## 1. Reconnaitre les tissus 

### 1.1 Les fibres textiles

* fibre naturelle
    - végétale
    - animale
    - végétale
* fibres synthétique 
    - polyesther (issu du pétrole)
    - viscose (chimique/artificielle)
    - polyamide (issu du pétrole) : nylon

### 1.2 Les tissus

- tissu tricoté (ex Jersey dans les sweats) : s'effiloche quand on le découpe, ne se détache pas/reste tissé
- tissu non-tricoté (feutre de laine, laine de roche) : fibre tassée/compressée, bord net quand on le découpe
- tissu tissé : enchevêtrement de fils ; fil de trame (vertical, soit on le met "au-dessus"(soulève), soit "en dessous"), fil de chaîne (horizontal ; avec un métier à tisser)
    - les armures : 
        - la toile (2x2)
        - le sergé (3x3) : ex le jean
        - le satin (5x5)
    - bien reconnaître l'endroit et l'envers
    - lisière (fil utilisé verticalement sur le tissu, comme le fil de trame) important : permet de reconnaître le droit fil qui est parallèle à la lisière
    - droit fil : jambes de pantalon
    - biais : + d'élasticité : utlisé pour le nivau de la ceinture du pantalon


## 2. Techniques de coutures à la main


* coudre de droite vers la gauche pour les droitiers
## 3. Machine à coudre

* on peut coudre maximum 6mm d'épaisseur sur les machines classiques
## 4. Application lors d'un projet

on aura eu le support de tel et la phochette qui va avec
iron maiden

# Lundi 16/02/26

## Commandes
- 100 euros de budget par personne
- Passer les commandes très rapidement

# Jeudi 19/02/26

- faire ses propres batteries = moins cher et plus libre sur la forme de la batterie

- **2 types de batteries (piles)**
    - primaire (jetables)
    - secondaires (rechargeables)

- **batteries primaires**
    - utilisable 1 fois
    - Lithium : système d'alarme
- **batteries secondaires**
    - Niquel Cadmium =  Cadmium vraiment toxique pour l'environnement (lumière des sorties de secours)
    - Niquel Metal Hybride = bonne durée de vie et eco-friendly
    - Lead acid = grosse capacité (300 Ah), mais inflammable avec le liquide acide ; libère de l'hydrogène qui est explosif avec l'oxygène
    - Lithium Ion = batterie qui nous apporte le plus de puissance par rapport à la masse (ex : drônes)
    - LiFePO4 : capacité moindre massique (plus lourde que le Lithium Ion)

## Batteries LiPo

- Lithium Ion 3,7V en tension nominale par bâton
- Lithium Ion 3,2V en tension nominale par bâton
- Forme cylindrique du bâton avec un tour inox constitue une protection (pas facilement perçable par rapport au Lithium polymère)
    - INR = mélange entre IMR et ICR

## Slide 11/22
- Ne pas charger à plus de 1C = 6000mA (6A)
- En général quand c'est pas précisé dans les indications, on peut charger à 1C
- 4S = 4 cellules en série (3,7*4 = 14,8V)
- 2P = 2 cellules en parallèle
- 4000 mAh * 14,8V = 59,20Wh (énergie stockée)

- Chaque cellule doit avoir la même te,dio, fr vharge
- BMS = Battery Management systèle



## Conception Batterie 2S

- **Tension nominale** : 7,4 V (2 x 3,7 V)
- **Tension de fin de charge** : 8,4 V (2 x 4,2 V)
- **Capacité** : 3450mAh
- **Courant de décharge continu max** : 8A
- **BMS** : Modèle 2S 8,4A

