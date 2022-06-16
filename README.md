# HomeAssistant

Groupe français Home Assistant : https://www.facebook.com/groups/homeassistantgroupefrance

## Bat-Geek 
Mon tableau de bord pour PC, smartphone, tablette
Compatible avec tous les supports, ce dashbord tient entièrement sur un ecran 13 pouces (ref MacBook Pro) et 1 colonne tient entièrement sur l'écran d'un smartphone (ref iphone 13 Pro). 

-----

## INTRODUCTION

Je vous propose ma configuration personnelle :
- Tableau de bord (lovelace UI mode) PC, mobile, tablette
- templates
- thèmes jour et nuit

Je ne suis pas un expert, je suis simplement un passionné, les codes ne sont peut-être pas écrits de la meilleure façon, mais j'ai réalisé ceci avec mes petites connaissances.

Je n'utilise pas Mushroom et autre, j'écris tout donc soyez indulgent ! 😊

Ca été très long à écrire, je modifie régulièrement les détails, ou quand j'ai des nouvelles idées. 

Je suis en mode UI.
 
Je ne scinde pas mes fichiers, donc tout est dans configuration.yaml. 
Il y a beaucoup de templates, je les rédige, et je les garde, mais ils ne servent pas tous ! 😉

J'ai fait le choix de publier ma configuration intégrale, même ce qui est potentiellement inutile mais que je conserve pour le moment. 

-----

### ⚠️ Complètement revisité pour cette nouvelle version : 

- Réécriture des templates button card  
- Modifications des sensor templates  
- Modifications des cartes  
- Nouvelles cartes  
- Nouveaux popup  
- amélioaration des thèmes jour et nuit 
- Corrections de bugs divers
- Et beaucoup d'autres changements ! 🤪
Le tout harmonisé grâce aux templates button card.

D'autres modifications viendront dans les prochaines mises à jour... 😇

-----
### Mise à jour mineure du 16 juin 2022 : 

- Suppression du taux d'humidité dans le le label des cartes pièces pour alléger le visuel 
- Taille du label des cartes pièces légèrement plus grosse 
- Couleur du texte des boutons badges selon conditions 
- Corrections de bugs icone et couleur des cartes Système 
- Corrections de bugs 

### 🎉 Mise à jour : Nouveautés du 15 juin 2022 : 

Carte activité 

![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/carte_activite.jpg)

En haut à droite, un nouveau bouton ouvrant un popup pour quelques réglages via un simple clic ! Ce menu s'étoffera au fil du temps...
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

Nouveaux boutons qui rempalcent les anciens boutons ronds...
J'ai écrit deux templates button card : 
- carte_ronde : Icone + name + info 
- carte_ronde_no_label : icone + name

Ce qui permet aux positions des éléments d'etre identiques dans les deux formats. 
Egalement en place dans les popup. 

![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/carte_ronde.jpg) ![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/carte_ronde_popup.jpg)

Ajout du bouton AdGuard et son popup (les annonces vocales Alexa ont migré dans le bouton "Appareils")

![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/carte_ronde.jpg) ![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/adguard_popup.jpg)

Nouveau popup du bouton Lumières (au dessus de la sidecar ou carte activité)
Un tap action sur une carte ouvre un second popup avec le détail des lumières de la pièce. 

![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/popup_lumieres.jpg) ![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/popup_lumieres_detail.jpg)

Nouveau popup météo (tap action sur la sidecar / carte activité)

![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/meteo.jpg)

Cartes personnes avec nouvelles options et nouveaux popup 

![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/persons.jpg)

Création des boutons pour déclencher les aspirateurs encore plus facilement dans les zones et pièces

![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/boutons_aspi.jpg)


-----
## THEMES

### Theme Bat Night
![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/dashboard_night.jpg)

### Theme Bat Day
![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/dashboard_clear.jpg)

### Theme avec l'alarme
![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/dashboard_alarm.jpg)

### Smartphone
![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/dashboard_smartphone.png)

-----
## POPUP

### Tableau de bord 1 page grace aux popup card ! 
![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/popup_1.jpg) ![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/popup2.jpg) ![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/popup_3.jpg) 
![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/popup_4.jpg) ![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/popup_5.jpg) 
![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/popup_6.jpg)

---------------------

 ## ORGANISATION

### Voici comment je m'organise : 

1ère colonne : Activité générale 
- bouton-badge : info rapide avec popup en tap action

![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/badges.jpg)

- cartes Alarmes : Cartes et leurs popup

![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/alarmes.jpg)

- carte ronde : Modes, lumières, et devices allumés, avec badge compteur, capteurs, AdGuard etc... et le tap action ouvre un popup complet 

![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/cartes_rondes.jpg)

- carte activité : calendrier / météo / activité / mise à jour (infos dynamiques) , tap action : météo détailléé 

2ème colonne : les pièces de la maison avec popups détaillés

![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/cartes_pieces.jpg)


3ème colonne : multimédia et appareils avec popups détaillés

4ème colonne : personnes et système avec popups détaillés


---------------------

## SETUP 

Mon setup :
- Raspberry 4 + SSD
- ConBee2
- Dongle Bluetooth 
- Box Internet Orange Livebox 4
- 3 cubes Tenda Nova MW6 parametrés en pont 

J'utilise Alexa en vocal, et HomeKit sur l'Apple Watch


Mes modules :

![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/modules.jpg)

Mes intégrations :

![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/integrations.jpg)

Mes intégrations  hacs:

![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/integrations_hacs.jpg)
![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/integrations_hacs2.jpg)

---------------------

## MERCI 😉

Si vous aimez quelque chose ici, likez 🌟 mon repo !
Si vous souhaitez m'offrir une petite bière 🍺 ou un café ☕️ : https://www.buymeacoffee.com/aurelrv ou https://www.paypal.com/paypalme/aaherve
Merci ! 

If you like anything here, be sure to 🌟 my repo !
If you want to offer me a little beer 🍺 or a coffee ☕️ : https://www.buymeacoffee.com/aurelrv or https://www.paypal.com/paypalme/aaherve
Thank you !