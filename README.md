# Mad Geek 2024
My dashboard compatible with PC, smartphone, tablet  
 

[![Facebook](https://img.shields.io/badge/Facebook-1877F2?style=for-the-badge&logo=facebook&logoColor=white)](https://www.facebook.com/groups/homeassistantgroupefrance) [![PayPal](https://img.shields.io/badge/PayPal-00457C?style=for-the-badge&logo=paypal&logoColor=white)](https://www.paypal.com/paypalme/aaherve)  


## Table of contents

**[`Dashboard`](#DASHBOARD)** | **[`Installation`](#INSTALLATION)** | **[`Changelog 2024-02-13`](#CHANGELOG)** | **[`Setup`](#SETUP)** | **[`Thanks`](#THANKS)** | **[`Donate`](#DONATE)** 


## INTRODUCTION

Content  :

- lovelace UI mode : **lovelace.yaml is a full copy from the HA UI editor** 
- Custom light and dark themes
- Sensor and template files

I'm not an expert, I'm just a hobbyist.  
The code is certainly not written in the best way, but I created this with my limited knowledge.  
I write everything myself, so please be understanding! 😊  

👉🏼 There will be changes as I regularly evolve my dashboard with my ideas.  




## DASHBOARD
  

![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/01.jpg)  

1. Themes :  
I have created two distinct themes, and I switch between them using automation based on sunlight.  

2. Television :  
The television card is a massive effort in button card template and sensor template. I am pleased with the outcome!  
For this card, you need :
   - sensor template
   -  template button card `base`
   -  template button card `tv_card`
   -  template button card `media_controls` (for controls buttons)
   -  template button card `tv_NAME-TV_card` (with entities)  
   - After that, writing the card in the dashboard is very simple!   

```yaml
type: custom:button-card
template:
  - tv_NAME-TV_card
````    

3. Magic Brightness Gauge :  
On the room cards, the brightness gauges are very special...
A room has several lights, and the gauge controls all the lights, which I didn't want ! 
Indeed, the ideal was to find a way to control only the lights that are already turned on!
If a lighting scene is in progress, and only 4 out of 10 lights are on, the gauge only affects those 4 lights! Brilliant!
Here's what's needed: 
    - a light group for the room, exemple :  `light.kitchen`
    - input_number, exemple : `input_number.brightness_kitchen`
    - in the dashboard card, call the template : `room_card_slider` 
    - automation : 

```yaml
alias: Brightness gauge kitchen
description: ""
trigger:
  - platform: state
    entity_id:
      - input_number.brightness_kitchen
    to: null
  - platform: state
    entity_id:
      - light.kitchen 
    to: "off"
condition: []
action:
  - if:
      - condition: state
        entity_id: light.kitchen
        state: "off"
    then:
      - service: input_number.set_value
        metadata: {}
        data:
          value: 1
        target:
          entity_id: input_number.brightness_kitchen
    else:
      - variables:
          value: "{{ states('input_number.brightness_kitchen') | int }}"
      - if:
          - condition: state
            entity_id: light.bubl1
            state: "on"
        then:
          - service: light.turn_on
            data:
              transition: 2
              brightness_pct: "{{ value }}"
            target:
              entity_id: light.bulb1
      - if:
          - condition: state
            ...etc...
````   


![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/02.jpg)  


![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/03.jpg)  
- Clicking on the `cog`icon ⚙️  at the bottom of the `Activity card` takes you to the `settings sub-view`.   
- This is where you can choose the elements that the `Activity card` should display, with simple `input boolean`, for example `input.boolean_light`  
All elements are dynamic with  `conditional card`, so if they are activated but do not contain any information, the Activity card will not display them. 
For example, if I choose to display lights in the menu, the card will only display the "Lights" line if there are any lights turned on.  
This allows for a less cluttered card.  

![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/04.jpg)  
The third column consists of camera recordings.  
To ensure that the images refresh in real-time, I created generic camera entities.  
It's a brilliant trick!   
Because an picture card doesn't refresh on its own...   
And I use  [Doods2 (My French documentation)](https://github.com/herveaurel/Docs/tree/main/Doods2) 

```yaml
camera.yaml
  - platform: local_file
    file_path: /media/detections/verifications/camera.entree/verifiee.jpg 
    name: entree_verifiee
````  

![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/05.jpg)  
*I see that I've chosen the wrong title for this screenshot... It's supposed to be 'Person Card,' of course! I'll correct it later... 😄*   
This Person card is full of surprises!  
I utilize smartphone sensors, Proximity and Waze integrations, as well as several sensor templates.  
Refer to template button card `person_complete_card`  
The icon is automatically the one chosen during the creation of a zone! And I've set a default icon if the zone is unknown.  
⚠️ Be sure to read the [CHANGELOG file ](https://github.com/herveaurel/HomeAssistant/blob/main/CHANGELOG.md)  for the `Proximity` integration  

![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/06.jpg)  


![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/07.jpg)  


![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/09.jpg)  


![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/10.jpg)  


![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/11.jpg) 


![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/12.jpg)  
A new card entirely written in the "button card" template called `vacuum_header`!  
And in the template button card named `vacuum_name` you'll need to modify your entities. After that, everything will be automatic.   
I love it!   
Paired with the slightly customized `custom:xiaomi-vacuum-map-card`, it's perfect!  

![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/13.jpg)  


![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/14.jpg)  


![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/15.jpg)  
- A new card entirely written in the decluttering-template` format!  
- We need to create a sensor template to retrieve volume information.   
- After that, writing the card in the dashboard is very simple!

```yaml
type: custom:decluttering-card
template: music
variables:
  - entity: media_player.la_salle_de_bain
  - gauge: sensor.salle_de_bain_progression
````  
  
![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/16.jpg)  
In the bathroom, I've created `Water Sounds` but it wasn't simple.
I'm using water sound detection via the Alexa Echo.
But it doesn't come up in Home Assistant.
So, I did this:
 - I created and injected an `input_button` into Alexa : `input_button.bruits_de_l_eau`
 - I created and injected an `input_boolean` into HA : `input_boolean.bruits_deau_sdb`
 - I created a routine in Alexa that activates the `input_button` when water is detected.
 - Automatisation Home Assistant : 
```yaml
alias: Bruits d’eau sdb
description: ""
trigger:
  - platform: state
    entity_id:
      - input_button.bruits_de_l_eau
  - platform: template
    value_template: >-
      {{as_timestamp(now()) -
      as_timestamp(states.input_button.bruits_de_l_eau.last_changed) > 80  }}
condition: []
action:
  - if:
      - condition: template
        value_template: >-
          {{as_timestamp(now()) -
          as_timestamp(states.input_button.bruits_de_l_eau.last_changed) > 80 
          }}
    then:
      - service: input_boolean.turn_off
        data: {}
        target:
          entity_id: input_boolean.bruits_deau_sdb
    else:
      - service: input_boolean.turn_on
        data: {}
        target:
          entity_id: input_boolean.bruits_deau_sdb
mode: restart
````  

Then, I created a `history-graph` card and an `custom:apexcharts-card`  based on the `input_boolean.bruits_deau_sdb`, and now I can cry while looking at my children's abuses! 😩  


![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/17.jpg)  


![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/18.jpg)  
This is one of the widely used French systems to have all the information about a child's schooling: the agenda, grades, evaluations, averages, homework assignments, punishments, tardiness, and more.  
All of this is made possible thanks to the fantastic work of  [delphiki ](https://github.com/delphiki) :
-  [Pronote ](https://github.com/delphiki/hass-pronote) 
-  [Pronote Cards ](https://github.com/delphiki/lovelace-pronote)   


![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/19.jpg)   


And more ! 


## CHANGELOG  


 [**Read the CHANGELOG file** ](https://github.com/herveaurel/HomeAssistant/blob/main/CHANGELOG.md) 



## INSTALLATION

⚠️ **It's not a one-click setup!**

Some knowledge is required before diving in:

- Install a few HACS integrations necessary for proper functionality. 

  The unavoidable :
  
  [Decluttering Card ](https://github.com/custom-cards/decluttering-card)  
  _Reuse multiple times the same card configuration with variables to declutter your config_

  [lovelace-card-mod ](https://github.com/thomasloven/lovelace-card-mod)  
  _Add CSS styles_
  
  [lovelace-layout-card ](https://github.com/thomasloven/lovelace-layout-card)  
  _Get more control over the placement of lovelace cards_
  
  [vertical-stack-in-card ](https://github.com/ofekashery/vertical-stack-in-card)  
  _To group multiple cards into a single sleek card_
  
  [button-card ](https://github.com/custom-cards/button-card)  
  _Lovelace button-card_
  
  [apexcharts-card](https://github.com/RomRider/apexcharts-card)  
  _Higly customizable graph card_
  
  [Lovelace Mini Graph Card](https://github.com/kalkih/mini-graph-card)  
  _Minimalistic graph card_
  
  [Paper Buttons Row](https://github.com/jcwillox/lovelace-paper-buttons-row)  
  _Adds highly configurable buttons that use actions and per-state styling_
  
  [bar-card](https://github.com/custom-cards/bar-card)  
  _Customizable Animated Bar card_

  [swipe-card](https://github.com/bramkragten/swipe-card)  
  _A Lovelace card that uses swiper to create a touch slider that lets you flick through multiple cards_

- I advise you to copy all the `decluttering templates` and `button card templates`. Create the right `sensor templates` :  I use them extensively and call them throughout the cards.  

- Know where to copy and paste each part, whether it's the sensor templates, the contents of Lovelace, or the button card templates.  

- Adjust the entities, remove the unnecessary ones, etc...  

You need to adapt it to your configuration!   

Dashboard created in 4 columns, thanks to the ayout card` available on HACS:  
- The tab is configured with View Type: `Horizontal layout-card` / width: 350 / max_cols: 4
- A `vertical stack` column is nested within a card with :   

```yaml
type: custom:layout-card
layout_type: masonry
layout:
  width: 280
cards:
````

I recommend that you install and use my themes for perfect optimization of my codes. If you prefer to use other themes, copy the "Additions for my lovelace" part into your favorite theme. 

And then starting to copy pieces of Lovelace.



## SETUP 

- Raspberry 4 + SSD
- USB Sonoff Zigbee 3.0
- Bluetooth Sena Parani UD100
- Orange Livebox 4
- Tenda Nova MW6 and 1 MW12 

I use Alexa for voice commands and Apple Home on the Apple Watch.




## THANKS

I work alone, I code almost everything with `custom:button-card`, I invent a lot of things, and lately, I've modernized my Dashboard, inspired by the wonderful work of my friend Quentin Cloos.
I don't copy his codes, I replicate them in my own way.
I invite you to take a look at his work, it's exceptional!   
[Mobile First ](https://github.com/clooos/Home-Assistant-Mobile-First) and [Bubble Card](https://github.com/Clooos/Bubble-Card).


Do you know the amazing gauges developed by André Fortuna Gouveia?
I love them! Thanks to him!    
[HATC-GAUGE-CARD ](https://github.com/tagcashdev/hatc-gauge-card)  

---------------------

## DONATE 

If you like it, please give my repo a star! 🌟  
To buy me a beer 🍺 , coffee ☕️, say thanks 🙏, or show some love ❤️‍🩹   
[![PayPal](https://img.shields.io/badge/PayPal-00457C?style=for-the-badge&logo=paypal&logoColor=white)](https://www.paypal.com/paypalme/aaherve) 

