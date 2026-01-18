# **2526_Maker_ClawMachine**

##  **Description du Projet**
Dans le cadre de l'**Option Maker 2025-2026** à l'ENSEA, mon projet est de concevoir une machine à pince (Claw Machine) miniature.

L'idée est de concevoir un système automatisé capable de déplacer une pince sur trois axes (X, Y, Z) pour saisir et relâcher des objets.


## **Sommaire**
1. [Principe de réalisation](#1-principe-de-réalisation)
2. [Organisation du dépôt](#2-organisation-du-dépôt)
3. [Rétro-planning](#3-rétro-planning)

## **1. Principe de réalisation**
Pour mener à bien ce projet, j'utiliserais différentes technologies de prototypage rapide qu'on va étudier en cours :

### **1.1 Conception Mécanique & Fabrication**
* **Châssis (LASER) :** Conception d'une structure externe légère et rigide via la découpeuse LASER.
* **Système d'axes (3D Print) :** Déplacement X-Y-Z assuré par des rails et supports modélisés sur mesure et imprimés en 3D.
* **Pince motorisée :** Assemblage de pièces imprimées en 3D actionnées par un servomoteur.


### **1.2 Électronique & Énergie**
* **PCB :** Conception d'un circuit imprimé pour centraliser le contrôle des moteurs, du joystick et du bouton.
* **Alimentation (LiPo) :** Fabrication d'un pack batterie LiPo avec BMS intégré pour assurer la sécurité et l'autonomie du système.

### **1.3 Gestion de projet & Livrables**
* **Versionning (Git) :** Utilisation de Git et GitHub pour le suivi du code source et des fichiers de conception.
* **Documentation :** Reporting continu sur ce README.md et sur la plateforme maker.ensea.fr.
* **Rendu final :** Code source complet, fichiers de fabrication et vidéo de démonstration de 90 secondes.



## **2. Organisation du dépôt**

* **[Project_Management](./Project_Management/)** : Contient le suivi de projet, le journal de bord hebdomadaire, la to do list.
* **[CAD](./CAD)** : Plans de découpe LASER et modèles 3D (pince, supports, rails).
* **[Hardware](./Hardware)** : Schémas électriques, fichiers de routage du PCB et liste des composants (BOM).
* **[Software](./Software)** : Code source pour le pilotage des moteurs et la gestion des entrées utilisateur.
* **[Media](./Media)** : Photos de l'avancement, captures d'écran CAO.

## **3. Rétro-planning**


```mermaid
gantt
    title Planning Hebdomadaire : Machine à Pince (2026)
    dateFormat  YYYY-MM-DD
    axisFormat  Sem %U

    Initialisation & Git           :active, s1, 2026-01-15, 4d
    CAD Pince & Documentation      :s2, 2026-01-19, 7d
    Impression 3D & Découpe Laser  :s3, 2026-01-26, 7d
    Conception PCB (Joystick)      :s4, 2026-02-02, 7d
    Soudure PCB & Pack LiPo        :s5, 2026-02-09, 7d

    Montage Mécanique & Câblage    :b1, 2026-02-16, 7d
    Projet libre & Début Code      :b2, 2026-02-23, 7d
    Dev. Code           :crit, b3, 2026-03-02, 7d

    section Phase 3 : Finalisation
    Pilotage Axes & Joystick       :b4, 2026-03-09, 7d
    Intégration Pince & Debug     :b5, 2026-03-16, 7d
    Tests & Montage Vidéo Insta   :b6, 2026-03-23, 7d
    Finalisation Doc & Vidéo      :b7, 2026-03-30, 7d
    Préparation Soutenance        :b8, 2026-04-06, 7d
    Soutenance Finale (13 Avril)        :milestone, m1, 2026-04-13, 0d
``` 
