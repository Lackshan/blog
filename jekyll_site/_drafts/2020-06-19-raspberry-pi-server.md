---
layout: post
title: "Raspberry Pi Home Server Part 1"
date: 2019-11-21 10:51:00
categories: 
---
Since I can't bring my Dell R710 on flights or fit it in university accomodation, I will be setting up a Raspberry Pi as my home server. I will be making a series of posts to document my adventures. In this installment I'll explain how I installed Fedora Server 32 and set up Ansible. You can find my Ansible config [here]().

https://fedoraproject.org/wiki/Architectures/ARM/Raspberry_Pi#Supported_Hardware

sudo arm-image-installer --image='/home/lackshan/Downloads/Fedora-Server-32-1.6.aarch64.raw.xz' --target=rpi3 --media=/dev/sdb --resizefs

This creates SD Card

Enable USB Boot

Enable SSH

Connect to WiFi

Secuirty