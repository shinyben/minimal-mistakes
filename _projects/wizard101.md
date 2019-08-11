---
title: "Wizard101 Automation"
excerpt: "Used browser automation and keyboard interactions to automate gameplay."
header:
  image: /assets/img/projects/wizard101/wizard-city.jpg
  teaser: /assets/img/projects/wizard101/wizard-city.jpg
gallery:
  - url: /assets/img/projects/wizard101/grub-guardian.png
    image_path: /assets/img/projects/wizard101/grub-guardian.png
    alt: "grub-guardian"
gallery2:
  - url: /assets/img/projects/wizard101/pet.jpg
    image_path: /assets/img/projects/wizard101/pet.jpg
    alt: "pet"

---

I've been playing the game Wizard101 since I was around 12, and again hit the same "I don't have enough time!" problem as I did with the [Patience Replacers](/projects/patience-replacers). To still be able to play and enjoy the game without some of the 'grinding' aspects, I made a few programs to make my life easier.

First, Grub Guardian. In Wizard101 there is a 'pet' mechanic, where you can equip a pet that gives you stat boosts relative to how much you've leveled it up. You level pets up by playing minigames, but those minigames take a lot of time. My solution was to use Python/selenium to automate interactions with the web browser.

I had a few challenges: selenium doesn't have a way to handle the 'Enable Flash?' popup that one has to click every time they want to run a flash game. I therefore just maximized the window and used the pynput.keyboard and win32api to manually input keystrokes and mouse clicks. I also had to use this (as well as image recognition) to interact with the flash game itself. Also, there is a captcha system for logging in, which I bypassed using a captcha solving service.

{% include gallery caption="A screenshot from the Grub Guardian minigame." %}

I put the program on an AWS EC2 instance, and it now runs daily, leveling up my pets without my having to play minigames over and over.

{% include gallery id="gallery2" caption="Example pet stats. In this case, the pet has been leveled up five times, and all the talents add to the wizard's damage stat." %}

Another aspect of Wizard101 is reagent collection. This is also rather 'grind-y' once one reaches higher levels of crafting (reagents are used in crafting recipes). I also made a program to guide my character to reagents throughout reagent-rich worlds and collect them if they are present. This is not yet running on EC2, as some form of hardware acceleration needed to play Wizard101 is unavailable on the Windows Server. It runs on my laptop.

Finally, I built a little webscraper to download the resources from http://www.wizard101central.com/wiki/.
