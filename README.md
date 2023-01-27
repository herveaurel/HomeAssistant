# HomeAssistant

Groupe français Home Assistant : https://www.facebook.com/groups/homeassistantgroupefrance

## 🤓 Mad Geek 
Mon tableau de bord compatible avec PC, smartphone, tablette

-----

## ℹ️  INTRODUCTION

Voici ma configuration personnelle :

- Tableau de bord (lovelace UI mode) PC, mobile, tablette
- templates
- thèmes jour et nuit

Je ne suis pas un expert, je suis simplement un passionné, les codes ne sont certainement pas écrits de la meilleure façon, mais j'ai réalisé ceci avec mes petites connaissances.
J'écris tout moi-même donc soyez indulgents ! 😊

Je modifie régulièrement les détails, ou quand j'ai des nouvelles idées. 

-----

## 🚧 INSTALLATION

Ce n'est pas du 1 click ! 

Il faut quelques connaissances avant de se lancer. 
- Installer quelques intégrations HACS nécessaires au bon fonctionnnement.
- Créer les bons sensor templates aussi, car je les utilise en masse et en appelle partout dans les cartes.
- Savoir ou copier/coller chaque partie, que ce soit les sensor templates, le contenu du lovelace, les templates button card... 
- Modifier les entités, supprimer celles en trop etc...

Il faut adapter à sa config ! 🙂

Dashboard réalisé en 4 colonnes, grâce à "layout card" disponible sur HACS :
- l'onglet est paramétré sur Type de vue : Horizontal (layout-card) / width: 350 / max_cols: 4
- une colonne "pile verticale" est imbriquée dans une carte "type: custom:layout-card" / "layout_type: masonry" / et a comme Layout options  "width: 280"


-----

## ℹ️  PRESENTATION

### CHANGELOG : journal des modifications

### version 2023.1.6

Note spéciale : Un très grand merci à mon ami André Fortuna Gouveia pour son coup de main, et ses jauges HATC-GAUGE-CARD dont voici le github : https://github.com/tagcashdev/hatc-gauge-card 👈🏼

Changements :

- création d'un nouveau template 'last_changed" : agacé par le "il y a..." qui prend trop de place, ce template crée automtiquement un label personnalisé affichant avec précision la durée du last changed.
    - valable que pour les "custom: button-card"
    - il faut supprimer toutes les valeurs "show_last_changed" de toutes les cartes
    - se met de base quand c'est une carte lumiere ou badge, si on n'en veut pas il faut ajouter "show_label: false" dans la carte
    - dans un autre type de carte, il faut ajouter "- last_changed" en template dans la carte 
![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/last_changed.jpg)

- modifications du style des carte_lumiere : uniformité avec les autres cartes, et style automatique pour que les éléments se placent correctement peu importe la taille de la carte
![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/carte_lumieres.jpg)

- carte lumière dans toutes les sous vues des pièces

- nouvel agencement de certains onglets : les pièces, alarme etc...

- nouvelle carte batterie
![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/carte_batterie.jpg)


### version 2023.1.5

Changements :
- carte lumières : nouvelle carte, pour uniformiser toutes les cartes lumières, et gagner de la place avec un meilleur visuel + contour lumineux afin de différencier avec les autres cartes allumées. 
![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/carte_lumieres.jpg)



### version 2023.1.4

Changements :
- j'ai supprimé mon fichier sensor.yaml et j'ai remis cette partie à la racine de configuration.yaml suite à un soucis de refresh des templates. 
- 🎉 button-card: je commence à travailler avec les variables ! Simplification des codes, uniformité, automatisation, tout est mieux avec les variables! Plusieurs cartes et templates button card impactés : Pièces, personnes, TV, carte_badge ...
- cartes pièces : le graph est de retour, et les label beaucoup plus complets et automatisés grâce aux variables 
- templates button-card: certains "state" passent en template pour diminuer le nombre de lignes du lovelace, comme "carte_bouton_state", ou "state_person" etc...
- nouvelles double jauges pour les jauges température / humidité (voir capture)
- carte Activité (sidebar) : boite aux lettres : ouverte / courrier relevé et en mode vacances : prochain passage de l’aspi prévu (voir capture) 
- onglet Alarme: nouveau bouton pour le prochain passage d'aspi prévu en mode vacances (voir capture) 
- onglet Lumières : changement des cartes pour un meilleur visuel (voir capture) 
- quelques changements graphiques par ci par là comme par exemple : 
    - inversement du gras entre name et label/state dans template "base" 
    - les boutons des capteurs dans les cartes pièces
    - modifications des couleurs des boutons en bas de la carte Activités



### version 2023.1.3

Changements :
- ajout de la valeur "var(--background-button-in-card)" dans chaque thèmes, pour la couleur du background des boutons dans les cartes. (une modification dans le thème s'applique instantanément sur tout le dashboard, plus pratique)
- changement dans tout le lovelace du code couleur par cette valeur 



### version 2023.1.2

Changements :
- corrections couleur de fond des boutons de mise à jour système, dans la carte Activité (template button card "sidebar")
- corrections bugs sur les thèmes
- améliorations de la carte Courrier : optoin "relevé courrier fait" via un bouton (un input, un sensor template), avec automatisation et notification avec choix de valider ou non le relevé lorsque le capteur de la boite s'active, ca sera parfait ! 

![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/carte_courrier.jpg)

- améliorations des cartes personnes : la jauge de la batterie affiche l'icone si en charge, le state si non en charge (template button card : carte_personne et carte_personne_prenom)

![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/carte-personne.jpg)



### version 2023.1.1

Changements :
- améliorations de la carte météo
- ajout de traduction sur les erreurs des aspirateurs dans le template "systeme_avertissement"

![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/popup_meteo.jpg)



### 🎉 version 2023.1

Changements :
- modifications des thèmes
- nouvelle carte Activité (https://github.com/herveaurel/HomeAssistant#la-carte-activité)
- nouvelle carte Météo 
- modifications des boutons en bas des cartes
- sous vues pieces : jauges pour les capteurs
- sous vues pieces : réorganisation de la page
- nombreux templates button card modifiés (sidebar,  carte_bouton,  carte_bouton_state, carte_personne_prenom)


-----


### 🥳 Complètement revisité pour cette nouvelle version 2023 : 

- Réécriture des templates button card  
- Modifications des sensor templates  
- Modifications des cartes  
- Nouvelles cartes  
- Nouveauté : les sous-vues ! (adieu les popup de Browser Mod) 
- Nouveaux thèmes
- Utilisation des jauges HATC-GAUGE-CARD, développées par mon ami André Fortuna Gouveia, dont voici le github : https://github.com/tagcashdev/hatc-gauge-card

Et beaucoup d'autres changements ! 🤪
Le tout harmonisé grâce aux templates button card.

D'autres modifications viendront dans les prochaines mises à jour... 😇

-----

## 🎨 THEMES

### Theme Mad Night
![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/dashboard_night.jpg)

### Theme Mad Geek
![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/dashboard_clear.jpg)

### Theme avec l'alarme
![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/dashboard_alarm.jpg)

### Smartphone
![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/dashboard_smartphone.png)

-----

## La carte Activité

![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/carte_activite.jpg)![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/carte_activite2.jpg)![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/carte_activite3.jpg)

🎉 Nouveautés :
- Un tap sur les jauges dirige vers les sous vues associées. 
- Un tap sur le bouton Adguard, switche automatiquement le ON/OFF
- Un tap sur l'un des bouton de mise à jour, fait apparaitre / disparaitre le détail en dessous

Afin de choisir les informations qui apparraissent dans la carte activité : en haut à droite, un bouton ouvrant une sous-vue pour quelques réglages via un simple clic !
Il est possible de choisir son thème, et de choisir ce qui sera affiché dans les informations dynamiques de la partie "Activité". 
Pour cela, créer simplement des input.boolean, comme par exemple : 
- input_boolean.sidecar_show_mode
- input_boolean.sidecar_show_porte
- input_boolean.sidecar_show_mouvement 
etc...

Il est également possible de créer une automatisation, basée par exemple sur l'état de l'alarme ou des présences, pour que les informations varient. En effet, peut-être pas besoin que tout soit affiché quand je suis à la maison, je peux consulter les autres cartes, mais quand je ne suis pas à la maison je veux voir toutes les informations rapidement... 😉

![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/popup_reglages.jpg)

Désormais l'icone d'une pièce prend la couleur réelle, ainsi qu'un dégradé de la couleur réelle pour la pastille et le fond de la carte : 

![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/piece.jpg)

- Badge automatique avec icone de la zone, ou absence d'une personne

![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/badge-personne.jpg)

- Popup de confirmation sur le tap action de certains boutons afin d'éviter des erreurs de manipulations

![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/confirmation.jpg)

-----
## 😎 ONGLETS ET SOUS-VUES

### Tableau de bord avec peu d'onglets...grâce aux sous-vues ! J'en ai 30, voici des exemples : 
![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/popup_1.jpg) ![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/popup_2.jpg) ![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/popup_alarme.jpg) ![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/popup_4.jpg) 
![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/popup_5.jpg) ![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/popup_6.jpg) 
![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/popup_7.jpg) ![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/popup_8.jpg)


---------------------

## 🖥️ SETUP 

- Raspberry 4 + SSD
- Clé USB Sonoff Zigbee 3.0
- Dongle Bluetooth Sena Parani UD100
- Box Internet Orange Livebox 4
- 2 cubes Tenda Nova MW6 parametrés en pont 

J'utilise Alexa en vocal, et HomeKit sur l'Apple Watch

## 🔧 Mes appareils 

Zigbee
- Capteurs portes : Xiaomi et Aqara
- Capteurs mouvements : Xiaomi et Aqara
- Capteurs vibration : Xiaomi et Aqara
- Eclairage : ampoule Hue, ampoule GLEDOPTO, ampoules Trust International B.V, ampoules JunYu, ampoules INNR, ampoule TZ3000_keabpigv, bandeau led LEDVANCE
- Prises : Xiaomi, Osram
- Sirène Heiman
- Interrupteurs : bouton Wireless Switch Xiaomi 
- Thermometre rond à écran Orvibo
- Cube Aqara
- Moniteur de qualité de l'air Aqara
- Détecteur de fuite Aqara
- Capteur température Aqara
- Guide de rideau Aqara
- Tête thermostatique de radiateur Aqara
- Sirène Zigbee Frient
- Clavier Zigbee Frient

Bluetooth
- capteurs plantes Xiaomi 
- thermometres ronds à écran Xiaomi 

Wifi
- Eclairage : ampoules couleurs, lampes de bureau, et bandeau led couleur Yeelight
- Sonnette Arlo Video Doorbell
- TV LG
- Alexa : Fire TV, Fire Cube, Echos Dot et Show 
- Imprimante Canon 
- Ruban led Sonoff intérieur 
- Lave-vaisselle Siemens 
- Aspirateurs : Roborock S50 et S6
- Interrupteur Shelly
- Caméra Aqara Hub G3
- Caméra Aqara Hub G2H Pro


Mes modules :

![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/modules.jpg)

Mes intégrations :

![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/integrations.jpg)

Mes intégrations HACS:

![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/integrations_hacs.jpg)
![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/integrations_hacs2.jpg)

---------------------

## ⭐️ VIP 

Si vous aimez , likez 🌟 mon repo !

Si vous souhaitez m'offrir une petite bière 🍺 ou un café ☕️, dire merci 🙏, me soutenir ❤️‍🩹, ou m'encourager 💪🏼, et devenir VIP ⭐️ pour une aide personnalisée par message privé : https://www.paypal.com/paypalme/aaherve
Merci ! 
