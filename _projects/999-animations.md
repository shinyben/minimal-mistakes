---
title: "Java Animations"
excerpt: "Created a collection of Java animations."
header:
  teaser: /assets/img/projects/animations/Circler.gif
gallery:
  - url: /assets/img/projects/animations/Circler.gif
    image_path: /assets/img/projects/animations/Circler.gif
  - url: /assets/img/projects/animations/ConcentricGentle.gif
    image_path: /assets/img/projects/animations/ConcentricGentle.gif
  - url: /assets/img/projects/animations/Fibonacci.gif
    image_path: /assets/img/projects/animations/Fibonacci.gif
  - url: /assets/img/projects/animations/Waves.gif
    image_path: /assets/img/projects/animations/Waves.gif
  - url: /assets/img/projects/animations/ForcedPerspective.gif
    image_path: /assets/img/projects/animations/ForcedPerspective.gif
gallery2:
  - url: /assets/img/projects/animations/ConnectedParticles2.gif
    image_path: /assets/img/projects/animations/ConnectedParticles2.gif
  - url: /assets/img/projects/animations/BouncingBalls.gif
    image_path: /assets/img/projects/animations/BouncingBalls.gif
gallery3:
  - url: /assets/img/projects/animations/Bodies.gif
    image_path: /assets/img/projects/animations/Bodies.gif
  - url: /assets/img/projects/animations/Bodies2.gif
    image_path: /assets/img/projects/animations/Bodies2.gif
  - url: /assets/img/projects/animations/ElasticGravityBall.gif
    image_path: /assets/img/projects/animations/ElasticGravityBall.gif
gallery4:
  - url: /assets/img/projects/animations/RoseFunctionsIncreasing.gif
    image_path: /assets/img/projects/animations/RoseFunctionsIncreasing.gif
  - url: /assets/img/projects/animations/Spirograph.gif
    image_path: /assets/img/projects/animations/Spirograph.gif
  - url: /assets/img/projects/animations/Spirograph2.gif
    image_path: /assets/img/projects/animations/Spirograph2.gif
  - url: /assets/img/projects/animations/Sierpinski.gif
    image_path: /assets/img/projects/animations/Sierpinski.gif
  - url: /assets/img/projects/animations/SierpinskiFinal.png
    image_path: /assets/img/projects/animations/SierpinskiFinal.png
gallery5:
  - url: /assets/img/projects/animations/EnhancedLife1.gif
    image_path: /assets/img/projects/animations/EnhancedLife1.gif
  - url: /assets/img/projects/animations/EnhancedLife2.gif
    image_path: /assets/img/projects/animations/EnhancedLife2.gif
---

Right before taking AP Computer Science in high school, I decided to do a little project (this would be my first, aside from the little Java games I had made from the <i>Programming Videos Games for the Evil Genius</i> book I had gotten). I wanted to make my own little collection of nice-looking animations/GIFs. I just wanted to mess around with colors and Java's draw functionality.

I started with drawing a ball on the screen. A stationary ball isn't very exciting, though, so I opted for giving the balls a velocity and acceleration. I also made their color dependent on their position on the screen, and made a function to slowly change the color from one to another.

{% include gallery %}

Next, I made the bounding box a border, and gave the balls a bouncing functionality.

{% include gallery id="gallery2" %}

I also added a planetary-style gravity, giving balls mass and a gravitational pull.

{% include gallery id="gallery3" %}

Finally, I made some mathematical patterns, such as rose functions, spirographs, and the Sierpinski triangle.

{% include gallery id="gallery4" %}

I also made what I called the Enhanced Game of Life, basically Conway's Game of Life where the player could modify rules on the fly.

{% include gallery id="gallery5" %}
