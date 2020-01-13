---
title: "Patience Replacers"
excerpt: "Designed and built a system to find and capture shiny Pokemon."
header:
  teaser: /assets/img/projects/patience-replacers/setup.png
gallery:
  - url: /assets/img/projects/patience-replacers/tepig.JPG
    image_path: /assets/img/projects/patience-replacers/tepig.JPG
gallery2:
  - url: /assets/img/projects/patience-replacers/budew.jpg
    image_path: /assets/img/projects/patience-replacers/budew.jpg
  - url: /assets/img/projects/patience-replacers/shiny-budew.jpg
    image_path: /assets/img/projects/patience-replacers/shiny-budew.jpg
gallery3:
  - url: /assets/img/projects/patience-replacers/shiny-livingdex.PNG
    image_path: /assets/img/projects/patience-replacers/shiny-livingdex.PNG

---

First, some backstory. Shiny Pokemon are incredibly rare (1/8192 chance of encounter) color variations on normal Pokemon. If a person continually searches for shiny Pokemon, it would take around 20 hours to find one in most Pokemon games.

As I don't have that kind of time, I decided to automate the process - letting an Arduino program encounter the Pokemon until a shiny was found.

My first attempt was mechanical - I used a couple servos to manually press buttons, and a light detecting resistor (LDR) to measure the light on the screen. The light then informed the Arduino what state the game was in. There a few issues with this state: the servos would lose power over time, and their reliability was spotty. They also made a lot of noise as they worked.

{% include gallery caption="The first shiny the mechanical version found." %}

I differentiated between shiny and normal Pokemon by the blackout time of the bottom screen - shinies have an extra animation when starting a battle, which lengthens the bottom screen's blackout time by a few milliseconds.

Wanting to make the system more reliable and less noisy, my next attempt was digital: I took apart the DS I was working with, soldered directly to the motherboard, and passed in the 3.3V required to simulate a button press. This was much easier to work with. The result is visible at the top of the page and below. I also added a counter on a LED screen to keep track of how many encounters it took.

{% include gallery id="gallery2" caption="A budew found by the soldered version." %}

Overall, I've built a few programs to handle different games and encounter types, and used the same method to modify a 2DS as well.

{% include gallery id="gallery3" caption="The current status of my shiny LivingDex." %}
