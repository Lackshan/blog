---
layout: post
title: "SMS Server"
date: 2020-06-18 18:05:00
categories: 
---
About 10 months ago I created an SMS Server for my father's clinic so that he could send his patients appointment reminders. The SMS Server was a Raspberry Pi 3 with a [Waveshare GSM HAT](https://www.waveshare.com/gsm-gprs-gnss-hat.htm) that ran a cron job every morning which would execute a python script. The Python script would check a Google Calendar for appointments, and if there were an upcoming appointment, it would remind the patient. I opted to use Google Calendar as it meant I wouldn't have to design a front end for the system and because the clinic staff had some experience with it. The SMS Server worked flawlessly for 6 months, at which point a combination of power outages and accidental hard shutdowns corrupted the SD Card. Since I'm in the UK and my father is in Malaysia, reflashing the SD Card was a little problematic. So the system lay dormant, waiting to be fixed. Since I'm free again, I thought I'd take another crack at it. I initially wanted to replace it with a DigitalOcean droplet and Twillio, however, Twillio charges $0.049 per SMS whereas Celcom Malaysia only charges $0.021 per SMS. Unfortunately, Celcom's API isn't public, so I've contacted them about it and am currently waiting for a reply.

Since the original code was hacked together and not documented (why do you think this blog is called Where's My Documention?), I will be rewriting the whole system from scratch. It will allow the user to choose between sending SMSs through a Raspberry Pi or Celcom's Omni service. You can find the repository [here](https://github.com/Lackshan/GCalSMS).

