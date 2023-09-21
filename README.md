# HomeAssistant

 [French group Home Assistant](https://www.facebook.com/groups/homeassistantgroupefrance)

## Mad Geek 
My dashboard compatible with PC, smartphone, tablet




## INTRODUCTION

Content  :

- lovelace UI mode : **lovelace.yaml is a full copy from the HA UI editor** 
- Custom light and dark themes
- Sensor and template files

I'm not an expert, I'm just a hobbyist.  
The code is certainly not written in the best way, but I created this with my limited knowledge.  
I write everything myself, so please be understanding! 😊  

👉🏼 There will be changes as I regularly evolve my dashboard with my ideas.  





## SCREENSHOTS
 

![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/01.jpg)  
![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/01-11.jpg)![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/01-12.jpg)  
![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/01-1.jpg)  
![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/02.jpg)  
![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/03.jpg)  
![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/04.jpg)  
![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/04-1.jpg)  
![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/05.jpg)  
![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/06.jpg)  
![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/07.jpg)  
![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/08.jpg)  
![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/09.jpg)  
![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/10.jpg)  
![alt text](https://github.com/herveaurel/HomeAssistant/blob/main/Captures/11.jpg)  


And more ! 




## INSTALLATION

**It's not a one-click setup!**

Some knowledge is required before diving in:

- Install a few HACS integrations necessary for proper functionality. 

  The unavoidable :
  
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

- Create the right sensor templates because I use them extensively and call them throughout the cards.
- Know where to copy and paste each part, whether it's the sensor templates, the contents of Lovelace, or the button card templates.
- Adjust the entities, remove the unnecessary ones, etc.

You need to adapt it to your configuration! 

Dashboard created in 4 columns, thanks to the "layout card" available on HACS:
- The tab is configured with View Type: Horizontal (layout-card) / width: 350 / max_cols: 4
- A "vertical stack" column is nested within a card with :   

````
type: custom:layout-card
layout_type: masonry
layout:
  width: 280
cards:
````

I recommend that you install and use my themes for perfect optimization of my codes. If you prefer to use other themes, copy the "Additions for my lovelace" part into your favorite theme. 

Then copying the button card templates.

And then starting to copy pieces of Lovelace.



## SETUP 

- Raspberry 4 + SSD
- USB Sonoff Zigbee 3.0
- Bluetooth Sena Parani UD100
- Orange Livebox 4
- Tenda Nova MW6 and 1 MW12 

I use Alexa for voice commands and Apple Home on the Apple Watch.




# THANKS

I work alone, I code almost everything with 'custom:button-card', I invent a lot of things, and lately, I've modernized my Dashboard, inspired by the wonderful work of my friend Quentin Cloos.
I don't copy his codes, I replicate them in my own way.
I invite you to take a look at his work, it's exceptional!   
[Mobile First ](https://github.com/clooos/Home-Assistant-Mobile-First) and [Bubble Card](https://github.com/Clooos/Bubble-Card).


Do you know the amazing gauges developed by André Fortuna Gouveia?
I love them! Thanks to him!    
[HATC-GAUGE-CARD ](https://github.com/tagcashdev/hatc-gauge-card)  

---------------------

## VIP 

If you like it, please give my repo a star! 🌟  
[If you'd like to buy me a beer 🍺 or a coffee ☕️, say thanks 🙏, show some love ❤️‍🩹 ](https://www.paypal.com/paypalme/aaherve)

