---
layout: project_page
title: Fall Detection for Elderly Patients
permalink: /proj/fall-detector
project_id: fall-detector
github_url: https://github.com/josecarita/fall_detector_using_vision_computer_and_IoT
---

Falls are one of the main causes of injury in older adults, and how quickly someone notices matters. This prototype for geriatric care watches a room with a camera on a Raspberry Pi, detects a fall automatically and alerts a caregiver, while streaming the patient's vital signs for remote follow-up.

### How it works

1. **Pose estimation.** MediaPipe Pose estimates the body landmarks on every frame.
2. **Fall rule.** The vertical position of the nose is tracked between frames. A sudden downward jump larger than 25% of the frame height is flagged as a fall.
3. **Alert.** The system sends one e-mail per fall event, with the frame and the detected skeleton attached, so a caregiver can check the situation immediately.
4. **Vital signs.** An Arduino with the e-Health sensor shield reads SpO₂, heart rate and ECG and sends them to the Raspberry Pi over UART.
5. **Dashboard.** A Flask server streams the annotated video and the sensor values to a web page, reachable remotely through remote.it.

### Stack

Python, MediaPipe, OpenCV, Flask, Raspberry Pi, Arduino, e-Health sensor shield.

### Limitations and next steps

The rule uses a single landmark and a fixed threshold, so sitting down quickly or bending can trigger false alarms. Next steps are to combine several landmarks (hips, shoulders), body orientation and "lying still after the event", and to report precision and recall on a public fall dataset.
