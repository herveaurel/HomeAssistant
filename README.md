# HomeAssistant

Groupe français Home Assistant : https://www.facebook.com/groups/homeassistantgroupefrance

## 🤓 Mad Geek 
Mon tableau de bord compatible avec PC, smartphone, tablette

-----

## ℹ️  INTRODUCTION

Voici ma configuration  :

- Tableau de bord (lovelace UI mode) PC, mobile, tablette
- configuration et templates
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

Je conseille d'installer mrs thèmes, puis de copier les templates button card, et ensuite de commencer a copier des morceaux du lovelace. 

-----

## ℹ️  PRESENTATION

### 🥳 Complètement revisité pour cette nouvelle version avril 2023 : 

(Voir le changelog pour les modifications)

Cette fois-ci, je ne peux pas proposer un changelog, c'est une nouvelle version !
Je travaille dessus depuis des mois, j'ai réécrit énormément de choses : 

- Réécriture complètes des templates button card  
- Modifications des templates  
- Modifications des cartes  
- Nouvelles cartes  
- Modifications des thèmes
- Utilisation des jauges HATC-GAUGE-CARD, développées par mon ami André Fortuna Gouveia, dont voici le github : https://github.com/tagcashdev/hatc-gauge-card

Et beaucoup d'autres changements ! 🤪

D'autres modifications viendront comme d'habirude, au rythme de mes idées... 😇

-----

##  THEMES ET TABLEAU DE BORD

![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/themes.jpg)

Quasiment chaque bouton renvoie à une sous vue. 

Par exemple, le bouton réglage en bas à droite de la carte Activité, permet de choisir en 1 clic les informations qui doivent etre affichées sur la carte. 😊

Quelques exemples de configurations possibles : 

![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/activite.jpg)

-----

##  ONGLETS

![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/lumieres.jpg)![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/aspis.jpg)![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/temp.jpg)![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/elec.jpg)![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/batteries.jpg)

-----
## SOUS-VUES

### Tableau de bord avec peu d'onglets...grâce aux sous-vues ! J'en ai 30, voici des exemples : 

![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/alarme.jpg)![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/personnes.jpg)![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/securite.jpg)![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/sejour.jpg)![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/agenda.jpg)![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/annonces.jpg)![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/systeme.jpg)![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/invites.jpg)


---------------------

## 🖥️ SETUP 

- Raspberry 4 + SSD
- Clé USB Sonoff Zigbee 3.0
- Dongle Bluetooth Sena Parani UD100
- Box Internet Orange Livebox 4
- 2 cubes Tenda Nova MW6 parametrés en pont 

J'utilise Alexa en vocal, et Maison Apple sur l'Apple Watch

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
- serrures Switchbot

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
- Caméra Reolink Argus 3


Mes modules :

![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/modules.png)

Mes intégrations :

![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/integrations1.png)
![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/integrations1.png)

Mes intégrations HACS:

![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/hacs-integrations.png)
![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/hacs-interface1.png)
![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/hacs-interface2.png)

---------------------

## ⭐️ VIP 

Si vous aimez , likez 🌟 mon repo !

Si vous souhaitez m'offrir une petite bière 🍺 ou un café ☕️, dire merci 🙏, me soutenir ❤️‍🩹, ou m'encourager 💪🏼, et devenir VIP ⭐️ pour une aide personnalisée par message privé : https://www.paypal.com/paypalme/aaherve
Merci ! 
