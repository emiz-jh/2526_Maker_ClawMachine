# Journal de bord

# 16/02/26

## Cahier des charges 

### Composants

* STM32 Nucléo L476RG
* Régulateur 12V-> 3.3V ou 5V : Würth Elektronik 173951275
* Moteurs pas à pas NEMA 17 (axe XY) 
    * Drivers de Moteurs TMC2225
* Moteur DC axe Z : Moteur jaune CC 3-6V
    * Driver DC 
* Moteur pour attraper/relacher : à trouver
* Limit switches : Micro-switch KW12
* Boutons :
    * attraper/relacher
* joystick : KY-023 Module ou joystick hw 504


Alim secteur 
https://fr.aliexpress.com/item/32859196804.html?src=google&pdp_npi=4%40dis!EUR!3.69!2.66!!!!!%40!12000022818679214!ppc!!!&traffic_server_nav=true&key=ggEu&src=google&albch=shopping&acnt=364-871-7393&isdl=y&slnk=&plac=&mtctp=&albbt=Google_7_shopping&aff_platform=google&aff_short_key=_oFgTQeV&gclsrc=aw.ds&&albagn=888888&&ds_e_adid=795091124544&ds_e_matchtype=search&ds_e_device=c&ds_e_network=g&ds_e_product_group_id=2519523730447&ds_e_product_id=fr32859196804&ds_e_product_merchant_id=5716905007&ds_e_product_country=FR&ds_e_product_language=fr&ds_e_product_channel=online&ds_e_product_store_id=&ds_url_v=2&albcp=23509535010&albag=194069405964&isSmbAutoCall=false&needSmbHouyi=false&gad_source=1&gad_campaignid=23509535010&gclid=Cj0KCQiA49XMBhDRARIsAOOKJHYtH11lq8Yg6SnbezyReU6-L-VEkoB1fVWWTsby6zUKKezJwBF_TuEaAsW3EALw_wcB


rail 20 20
* equerre profile angle 3d
* boitier 


### PCB

1. Le Cœur du PCB (Interface Nucleo)
Connecteurs femelles (2x38 pins) : Pour enficher ta Nucleo L476RG. Utilise les connecteurs extérieurs (Morpho) pour avoir accès à toutes les pins, ou les connecteurs "Arduino style" si tu veux une carte plus compacte.

2. Alimentation et Régulation
Embase Jack DC (2.1mm) : Pour brancher ton bloc 12V.

Condensateur de découplage Entrée : 100µF à 470µF (Chimique, 25V) à placer juste après le Jack.

Le Régulateur Würth (173951275) : Il va transformer ton 12V en 5V pour alimenter la Nucleo (pin 5V) et les capteurs.

Condensateur de sortie : 10µF (Céramique) proche de la sortie du régulateur Würth (selon la datasheet).

3. Drivers Moteurs Pas à Pas (X et Y)
2 supports pour modules TMC2225 : (Format StepStick, généralement 2x8 pins femelles).

Condensateurs de puissance (VMOT) : 1 condensateur chimique de 100µF (25V) par driver, placé au plus près de la pin VMOT du driver. C’est crucial pour protéger les TMC2225.

Connecteurs moteurs : 2 connecteurs JST-XH 4 pins (ou borniers à vis) pour relier les câbles des NEMA 17.

4. Drivers Moteurs DC (Z et Pince)
Pour l'axe Z (moteur jaune) : Un mini pont en H type DRV8833 ou MX1508 (très courant pour les moteurs jaunes). Ils sont minuscules et gèrent très bien le 3-6V.

Pour la Pince : * Option A : Si tu utilises un servomoteur (plus simple mécaniquement), prévois juste un connecteur 3 pins (GND, 5V, PWM).

Option B : Si c'est un moteur DC, utilise le deuxième canal du DRV8833.

Connecteurs : Borniers 2 pins pour les moteurs.

5. Entrées/Sorties (Connectique)
Connecteurs Limit Switches (X, Y, Z) : 3 connecteurs JST-XH 2 pins.

Connecteur Joystick : 1 connecteur 5 pins (GND, 5V, VRx, VRy, SW).

Connecteur Bouton "Attraper" : 1 connecteur 2 pins.

