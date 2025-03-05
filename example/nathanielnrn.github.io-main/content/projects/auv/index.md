+++
title = "CUAUV"
description = "CUAUV is an autonomous underwater vehicle team that annually builds an autonomous submarine to compete in the RoboSub competition."
weight = 2

[extra]
local_image = "projects/auv/subs.png"
+++


<div style="font-size:0.8em" >

For 3 years I worked with 50 cross-disciplinary teammates to annually create an
autonomous submarine and compete in [Robosub](https://robonation.org/programs/robosub/).
In particular, I have contributed to our submarines'
control optimizer, computer vision systems, and PID tuner with implementations
in Python, often utilizing OpenCV libraries.

</div>

---

[CUAUV](https://cuauv.org) is a Cornell Project Team that annually creates an
autonomous underwater vehicle for competition in [Robosub](https://robonation.org/programs/robosub/).
The submarine uses a from-scratch software stack to understand the world around
it, control itself, and remain functional in the face of disturbances.
The team is made up of 50 members, with 4 subteams: Business, Electrical,
Mechanical, and Software.

As a Software member, over 3 years I worked with ~12 teammates on improving our
submarine's software. Initially, my work focused on computer vision
and locomotion logic. Over time, my work gradually specialized to improving our
control system and associated tools and algorithms.


{% resize_image(path="sub-work.jpg", width=800, height=481, op="fit") %}
Examining a loose connection on our submarine at our weekly pool test.
{% end %}



My work was done in Python, utilizing a Dockerized Linux development environment.



#### CUAUV development happens on a private repo and can be viewed upon request {.centered-text}

## Contributions

 - Optimized **control system**, incorporating a closed-loop PID system, a
 desire-to-thrust optimizer, and updated pwm-to-thrust curves with empirical measurements.
 Our control system produces a responsive and predictively-behaved submarine.[^1]
 - Tuned **CV algorithms** incorporating SIFT, contour denoising, and associated
 locomotion logic.
 - **Auto-PID-tuner** rewrite that utilizes [Zeigler-Nichols](https://en.wikipedia.org/wiki/Ziegler%E2%80%93Nichols_method)
 to caculate PID values that produce desired behavior. This rewrite included
 updated logic and quality of life improvements for the auto-tuner and associated
 tools.

 [^1]: Documentation on control work can be found [here](auv-controls.pdf).
 See the implementation section.
