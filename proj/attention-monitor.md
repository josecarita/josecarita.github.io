---
layout: project_page
title: Remote-Class Attention Monitor
permalink: /proj/attention-monitor
project_id: attention-monitor
github_url: https://github.com/josecarita/Pupil_detection
---

In remote classes a teacher cannot see whether students are following. This prototype looks at the student through the webcam and labels each frame as attentive or not attentive.

### How it works

1. MediaPipe Face Detection finds the face and returns the position of both eyes.
2. The line between the eyes gives the head tilt angle.
3. If no face is visible, or the tilt is beyond ±40° (head resting or turned away), the frame is labeled not attentive.

It runs in real time on a webcam stream, or in batch mode on a folder of images.

### Next steps

Judge attention from the eyes themselves: eye openness with the Eye Aspect Ratio from MediaPipe Face Mesh, gaze direction from the iris landmarks, and an attention score over time instead of a per-frame label, all processed locally for privacy.
