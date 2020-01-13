---
title: "AutoVid: Autocompiling YouTube Videos"
excerpt: "Used browser automation and FFMPEG in combination to create an automatic YouTube upload pipeline."
header:
  teaser: /assets/img/projects/autovid/channel.png

---

This was a large multi-thousand-line project I did in the summer of 2019. My goal was to create a pipeline such that I could leave a server running that would create YouTube videos on its own and upload them to YouTube, accruing views without my having to do any work. An example of the Reddit pipeline is [here](https://www.youtube.com/watch?v=M48NftKUFS4), and the TikTok pipeline [here](https://www.youtube.com/watch?v=ag5_ESjyInM).

The first attempt was a text-to-speech (TTS) Reddit post reader. There were a few different aspects of this pipeline: finding the post, extracting the pictures and text, creating the video, and uploading the video.

First, Selenium, a web automation library, would be used to pull up the webpage that contained the list of popular Reddit posts that had been created on a particular day.

Next, those posts and their comments would be explored, again using the DOM to interact with the website to filter popular posts, screenshot them, and compile their text. Once I had a picture of the original post and the popular comments, as well as their text, I could create the video.

To create the video, I made a standard format. First, the original question asked, such as "What’s an invention that’s still around today but has lost sight of its original purpose?" would be shown, and then its most popular comments, such as "Electric Pen by Edison are now tattoo machines." These would have TTS and fun background music broadcast over them. The screenshots would be combined via FFMPEG into a sort of slideshow, and they would stay on the screen for as long as the TTS was still vocalizing the comment's text. I also had to create a thumbnail image programmatically, which I did with the PIL library.

Uploading the video consists of logging into a YouTube account and navigating the uploading process, from selecting a file to specifying a title and description. This was all done programmatically as well.

I used AWS to automate the process, making the software compatible with Windows, Linux, and MacOS. After completion of the project, I found out that a GitHub repo had been opened during the time that I was coding that did the exact same thing as us, but professionally: with a better TTS client and a neat sentence-by-sentence revealing mode on each comment. We made their code compatible with Linux and transitioned to using it exclusively.

The next project, the automated TikTok videos, had the same process for uploading, but the body of the video was different. We navigated to TikTok.com, found the most popular videos of the day, and downloaded them. We also used a VPN (which I interacted with via the DOM, a hard problem) to find the most popular videos in India and around 10 other countries. We then concatenated those videos to create a 10-minute video, which was then uploaded to YouTube.

In summary, I created an auto-uploading pipeline for both Reddit and TikTok videos, and let it run automatically for a short while. This project utilized Python, Selenium, FFMPEG, and TTS systems.
