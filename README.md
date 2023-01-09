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

![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/carte_activite.jpg)

Afin de choisir les informations qui apparraissent dans la carte acticité : En haut à droite, un bouton ouvrant une sous-vue pour quelques réglages via un simple clic ! Ce menu s'étoffera au fil du temps...
Il est possible de choisir son thème, et de choisir ce qui sera affiché dans les informations dynamiques de la partie "Activité". 
Pour cela, créer simplement des input.boolean : 
- input_boolean.sidecar_show_mode
- input_boolean.sidecar_show_porte
- input_boolean.sidecar_show_mouvement (nouveau template dans configuration.yaml)
- input_boolean.sidecar_show_lumiere
- input_boolean.sidecar_show_autre
- input_boolean.sidecar_show_connecte

Mettre à jour le nouveau template button card de la sidecar. 

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

### Tableau de bord avec peu d'onglets...grace aux sous-vues ! J'en ai 30, voici des exemples : 
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
- thermometres ronds à ecran Xiaomi 

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

Mes intégrations  hacs:

![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/integrations_hacs.jpg)
![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/integrations_hacs2.jpg)

---------------------

## ⭐️ VIP 

Si vous aimez , likez 🌟 mon repo !

Si vous souhaitez m'offrir une petite bière 🍺 ou un café ☕️ , dire merci 🙏 , me soutenir ❤️‍🩹, ou m'encourager 💪🏼, et devenir VIP ⭐️ pour une aide personnalisée par message privé : https://www.buymeacoffee.com/aurelrv ou https://www.paypal.com/paypalme/aaherve
Merci ! 
