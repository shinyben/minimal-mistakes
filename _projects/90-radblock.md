---
title: "RadBlock: The First AI AM/FM Ad-Blocker"
excerpt: "Used machine learning to discern between radio ads and songs."
header:
  teaser: /assets/img/projects/radblock/website.png

---

My largest project yet. There are quite a few components to this one: collection/storage/cleaning of radio data, the model itself, the database of stations and their respective statuses, the front-end website [here](http://radio-search.com/). I'm not going to go into much detail in this description because I would like to be able to capitalize on the idea, but I will give a general sense of what I did.

First, the database. I found a few disparate databases around the web, including the FCC database, and compiled them into a central CSV that I used to populate a MongoDB instance. I have pipelines that I can run to automatically this central CSV from new FCC and other data daily as well.

Once I had the database, I built the website around it. It allows for State/Station lookup, and while it doesn't have much database information publicly-facing (I still have to find a way to limit the amount of requests one IP address can make per day so I don't get all my data scraped), it gives the gist, what you can find on the FCC website. I also have a live indicator for around 700 stations - whether they're currently playing ads or not.

As for the model: I will say that it's transitioned past the copy-and-paste basic model stage. Even that was decent, though: 98+% intra-station accuracy on country, the most prevalent radio genre, and ~90% accuracy transferring between genres, classifying on relatively short frequency blocks. I had to manually label 20+ hours of audio data using Audacity, and create a pipeline to split the .wav files I had into ads and not ads.

I also populated the database with direct livestream links, which allows me to use AWS to run inference on those stations' livestreams and update Mongo with the result. This is hard because there's no central spot where all livestream links are stored, which forced me to use a lot of browser automation (interacting with the DOM) and messing with HTTP requests to programmatically find the stream locations. I have around 25% total coverage of all internet radio stations right now (~3k stations all together), and will need to manually find most of the other links on my own.

I think this will be useful for stereo companies with internet connection enabled boxes (say like Tesla). They will be able to deny advertisers' access to their customers. Therefore stereo manufacturers could sell a premium ad-free radio experience or sell access to their user base to stations or advertisers. Radio ads are a $18b market in the US, and I'm hoping that this tech can make a significant splash.  
