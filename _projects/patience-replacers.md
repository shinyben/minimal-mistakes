---
title: "Patience Replacers"
excerpt: "Designed and built a system to find and capture shiny Pokemon."
header:
  image: /assets/img/projects/patience-replacers/setup.png
  teaser: /assets/img/projects/patience-replacers/setup.png
gallery:
  - url: /assets/img/projects/patience-replacers/tepig.JPG
    image_path: /assets/img/projects/patience-replacers/tepig.JPG
---

First, some backstory. Shiny Pokemon are incredibly rare (1/8192 chance of encounter) color variations on normal Pokemon. If a person continually encounters Pokemon, it would take around 20 hours to find a shiny in most Pokemon games.

As I don't have that kind of time, I decided to automate the process - letting an Arduino program encounter the Pokemon until a shiny was found.

My first attempt was mechanical - I used a couple servos to manually press buttons, and a light detecting resistor (LDR) to measure the light on the screen. The light then informed the Arduino what state the game was in. There a few issues with this state: the servos would lose power over time, and their reliability was spotty. They also made a lot of noise as they worked.

{% include gallery caption="The first shiny my program found." %}

I differentiated the shiny and normal Pokemon by the blackout time of the bottom screen - shinies have an extra animation when starting a battle, which lengthens the encounter by a few milliseconds.

My next attempt was digital: I took apart the DS I was working with, wired the Arduino directly to the motherboard, and passed in the 3.3V required to simulate a button press. This was much easier, and much more reliable. The result is visible at the top of the page.

Overall, I've built a few programs to handle different games and encounter types, and used the same method to modify a 2DS as well.
