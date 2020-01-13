---
title: "WhoseArt: Demo AI Startup"
excerpt: "Created a CNN & webapp to identify 50 popular artists' works."
header:
  teaser: /assets/img/projects/whoseart/predicted.PNG
gallery:
  - url: /assets/img/projects/whoseart/predict.PNG
    image_path: /assets/img/projects/whoseart/predict.PNG
---

I started getting into AI/ML after taking 6.034 at MIT (Introduction to Artificial Intelligence), and decided to create a demo webpage for a possible future AI startup.

I used a CNN that I had trained on 50 famous artists as the backend, but aside from that made it with easy transfer in mind. It would be easy to take the current build and change it into a medical imaging webapp ready for paying users, for example.

I built it off [flaskSaaS](https://github.com/alectrocute/flaskSaaS), incorporating a login and Stripe payment gate to make it user-ready.

{% include gallery caption="What the prediction page looks like after you select your art piece." %}
