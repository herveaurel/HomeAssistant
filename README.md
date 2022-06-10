# HomeAssistant

Groupe français Home Assistant : https://www.facebook.com/groups/homeassistantgroupefrance

---Pour les changements mineurs, lisez le changelog---

Bat-Geek 
Mon tableau de bord pour PC, smartphone, tablette
Compatible avec tous les supports, ce dashbord tient entièrement sur un ecran 13 pouces (ref MacBook Pro) et 1 colonne tient entièrement sur l'écran d'un smartphone (ref iphone 13 Pro). 

---------------------

⚠️ Complètement revisité pour cette nouvelle version, les changements majeurs sont : 

- modifiactions des codes, templates, template button card ! 🥳
- créations de base templates pour unifier les cartes et les boutons 
- option retour à la ligne automatique dans tous les button card 
- nouvelle carte Activité, réalisée avec button card, entièrement dynamique et icone météo MDI animé
- amélioaration des thèmes jour et nuit 
- Corrections de bugs divers
- Et beaucoup d'autres changements ! 🤪

D'autres modifications viendront dans les prochaines mises à jour... 😇

Exemple :

Carte activité 
![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/meteo_modif.jpg)

Cartes personnes avec nouvelles options et nouveaux popup 
![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/persons.jpg)

Création des boutons pour déclencher les aspirateurs encore plsu facilement dans les zones et pièces
![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/boutons_aspi.jpg)



---------------------

Theme bat_Night
![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/dashboard_night.jpg)

Theme bat_Night with alarm
![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/dashboard_alarm.png)

Theme bat_Day
![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/dashboard_clear.jpg)

Mobile
![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/dashboard_smartphone.png)

Tableau de bord 1 page : popup card ! 
![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/popup.png)

---------------------
 
Voici comment je m'organise : 

1ère colonne : Activité générale 
- bouton-badge : info rapide avec popup en tap action
- cartes Alarmes : Cartes et leurs popup
- bouton-rond : Modes, lumières, et devices allumés, avec badge compteur, capteurs, annonces etc... et le tap action ouvre un popup complet 
- carte activité : calendrier / météo / activité / mise à jour (infos dynamiques) , tap action : météo détailléé 
![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/colonne_activite.jpg)

2ème colonne : les pièces de la maison avec popups détaillés
![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/colonne_pieces.png)

3ème colonne : multimédia et appareils avec popups détaillés

4ème colonne : personnes et système avec popups détaillés


---------------------

Je vous propose ma configuration personnelle :
- Tableau de bord (lovelace UI mode) PC, mobile, tablette
- templates
- thèmes jour et nuit

Je ne suis pas un expert, je suis simplement un passionné, les codes ne sont peut-être pas écrits de la meilleure façon, mais j'ai réalisé ceci avec mes petites connaissances.

Ca été très long à écrire, je modifie régulièrement les détails, ou quand j'ai des nouvelles idées. 

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

Je suis en mode UI.
 
Je ne scinde pas mes fichiers, donc tout est dans configuration.yaml. 
Il y a beaucoup de templates, je les rédige, et je les garde, mais ils ne servent pas tous ! 😉

J'ai fait le choix de publier ma configuration intégrale, même ce qui est potentiellement inutile mais que je conserve pour le moment. 

Si vous aimez quelque chose ici, likez 🌟 mon repo !
If you like anything here, be sure to 🌟 my repo !

Si vous souhaitez m'offrir une petite bière 🍺 ou un café ☕️ : https://www.buymeacoffee.com/aurelrv ou https://www.paypal.com/paypalme/aaherve

If you want to offer me a little beer 🍺 or a coffee ☕️ : https://www.buymeacoffee.com/aurelrv or https://www.paypal.com/paypalme/aaherve

Merci ! 
Thank you !