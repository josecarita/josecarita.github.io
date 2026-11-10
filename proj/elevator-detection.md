---
layout: project_page
title: Elevator Person Detection
permalink: /proj/elevator-detection
project_id: elevator-detection
github_url: https://github.com/josecarita/Person-detection
---

An elevator controller needed a simple condition: is anyone inside the car? A camera and a Raspberry Pi provide that signal without extra sensors, for example to avoid sending an empty car or to confirm the car is empty before a maintenance action.

### How it works

Each frame is processed with OpenCV's HOG descriptor and its pre-trained SVM people detector. If at least one person is detected, GPIO pin 7 goes high, which can drive a relay or an input of the elevator controller.

### Next steps

Replace HOG with a lightweight deep model for better accuracy in crowded cars, count occupants instead of a yes/no signal, and add a short time filter so one missed frame does not toggle the output.
