# Edge_Quiz

## All Lab links:
Lab 1: https://github.com/drfuzzi/INF2009_Setup/tree/main

Lab 2: https://github.com/drfuzzi/INF2009_SoundAnalytics

Lab 3: https://github.com/drfuzzi/INF2009_ImageAnalytics

Lab 4: https://github.com/drfuzzi/INF2009_VideoAnalytics

Lab 5: https://github.com/drfuzzi/INF2009_DLonEdge

Lab 6: https://github.com/drfuzzi/INF2009_MQTT

Lab 7: https://github.com/drfuzzi/INF2009_AWSIoTCore

Lab 8: https://github.com/drfuzzi/INF2009_EdgeImpulse


Section 1: Raspberry Pi OS Installation & Initial Configuration
MCQs
Which software tool is used to write the Raspberry Pi OS image to a microSD card?
A. Etcher
B. Raspberry Pi Imager
C. Rufus
D. Win32 Disk Imager
Answer: B. Raspberry Pi Imager

When using Raspberry Pi Imager, which setting would you adjust to configure WiFi credentials before booting for the first time?
A. Localisation settings
B. OS Customisation settings
C. Advanced display settings
D. Timezone settings
Answer: B. OS Customisation settings

Short Answer
In the Raspberry Pi Imager’s advanced settings, name two items you can configure before flashing the microSD card.
Answer:

Hostname of the Raspberry Pi

Username and password

WiFi credentials (SSID and password)

SSH enabling

Locale settings (timezone, keyboard layout)

What is the command to update the list of available packages on a Raspberry Pi running Raspberry Pi OS?
Answer: sudo apt update

What is the command to upgrade all currently installed packages on a Raspberry Pi?
Answer: sudo apt upgrade

Section 2: Hardware Setup & Basic Configuration
MCQs
Which of the following components is not strictly required to get the Raspberry Pi 400 up and running with a webcam?
A. MicroSD card with Raspberry Pi OS
B. Power supply
C. Ethernet cable
D. USB webcam
Answer: C. Ethernet cable (WiFi can be used instead.)

To enable VNC on a headless Raspberry Pi via SSH, which tool do you typically use?
A. raspi-config
B. config.txt
C. sudo raspi-config
D. /boot/cmdline.txt
Answer: C. sudo raspi-config

Short-Answer
Which command would you run to edit the network configuration file (dhcpcd.conf) on Raspberry Pi OS?
Answer: sudo nano /etc/dhcpcd.conf

Explain why assigning a static IP to your Raspberry Pi can be useful in a lab environment.
Answer: It ensures the Pi always has the same IP address, making it easier to connect via SSH or VNC without repeatedly looking up the IP.

Section 3: Using SSH and VNC
MCQs
Which of the following protocols is used by VNC to provide a graphical desktop over the network?
A. RDP (Remote Desktop Protocol)
B. RFB (Remote Framebuffer Protocol)
C. SSH (Secure Shell)
D. FTP (File Transfer Protocol)
Answer: B. RFB (Remote Framebuffer Protocol)

Short-Answer
What is the default port used by VNC on a Raspberry Pi?
Answer: Port 5900

State one way to find your Raspberry Pi’s IP address on a local network if you do not have direct access to its desktop.
Answer:

Check the device list on your router or mobile hotspot

Use arp -a on your local machine

Use a network scanning tool (e.g., nmap)

Section 4: Webcam Setup & Testing
MCQs
Which command-line tool is typically used to capture a still image on the Raspberry Pi with a USB webcam?
A. motion
B. fswebcam
C. raspistill
D. gstreamer
Answer: B. fswebcam

What is the Linux subsystem or driver model used for webcams on Raspberry Pi OS?
A. ALSA
B. Video4Linux2 (v4l2)
C. GStreamer
D. MESA
Answer: B. Video4Linux2 (v4l2)

Short-Answer
Write the exact command to capture a 1280×720 image named image.jpg using fswebcam without displaying the banner text.
Answer: fswebcam -r 1280x720 --no-banner image.jpg

Which command is used to list all USB devices connected to the Raspberry Pi?
Answer: lsusb

Section 5: Audio Input & arecord
MCQs
Which command can be used to record audio on a Raspberry Pi from a recognized microphone?
A. aplay
B. ffmpeg
C. arecord
D. sox
Answer: C. arecord

If your webcam’s microphone is recognized as card 2, device 0, which of the following commands records a 10-second clip?
A. arecord -D plughw:0,2 -d 10 test.wav
B. arecord -D plughw:2,0 -d 10 test.wav
C. arecord -D hw:2,0 -d 10 test.wav
D. arecord -d 10 test.wav
Answer: B. arecord -D plughw:2,0 -d 10 test.wav

Short-Answer
What is the command to play back the recorded audio file test.wav?
Answer: aplay test.wav

If you cannot hear any audio on playback, mention one troubleshooting step you might try.
Answer:

Check alsamixer to ensure the volume isn’t muted

Ensure correct audio output (HDMI vs. headphone jack)

Verify the proper audio device is selected

Section 6: Video Recording with ffmpeg
MCQs
Which flag specifies the video input format when using ffmpeg on a Raspberry Pi with a USB webcam?
A. -i
B. -r
C. -video_size
D. -f
Answer: D. -f

In the command below, what does the -framerate 25 parameter control?
ffmpeg -f v4l2 -framerate 25 -video_size 640x480 -i /dev/video0 output.mp4
A. The bitrate
B. The resolution
C. The capture frames per second
D. The audio sampling rate
Answer: C. The capture frames per second

Short-Answer
Write a sample ffmpeg command to record a 30-second video clip from /dev/video0 at 800×600 resolution into a file called myvideo.mp4.
Answer: ffmpeg -f v4l2 -t 30 -video_size 800x600 -i /dev/video0 myvideo.mp4

Section 7: Virtual Environments & Python
MCQs
Which command is used to create a Python virtual environment named myenv?
A. python3 -m venv myenv
B. virtualenv myenv
C. mkvenv myenv
D. pip install myenv
Answer: A. python3 -m venv myenv

After creating a virtual environment, which command do you use to activate it on a Raspberry Pi OS (bash shell)?
A. enable myenv
B. bash myenv
C. source myenv/bin/activate
D. activate myenv
Answer: C. source myenv/bin/activate

Short-Answer
Why is it recommended to use a Python virtual environment when installing packages like opencv-python?
Answer: It prevents version conflicts by isolating package installations from the system-wide Python packages, keeping your global environment clean.

Section 8: Motion Detection & OpenCV Basics (Advanced/Optional)
MCQs
Which OpenCV function is commonly used to convert a frame to grayscale?
A. cv2.absdiff
B. cv2.cvtColor
C. cv2.threshold
D. cv2.findContours
Answer: B. cv2.cvtColor

In a simple motion detection script using OpenCV, which function is used to find the outlines of detected shapes or movements?
A. cv2.GaussianBlur
B. cv2.dilate
C. cv2.absdiff
D. cv2.findContours
Answer: D. cv2.findContours

Short-Answer
Briefly explain what the following line of code does in a motion detection script:
frame_delta = cv2.absdiff(gray1, gray2)
Answer: It calculates the absolute difference between two grayscale frames (gray1 and gray2), highlighting the regions where changes (motion) occur.

What is one practical use of a Python-based motion detection system on a Raspberry Pi?
Answer: Home security or surveillance, wildlife monitoring, or triggering automated tasks when movement is detected.

Section 9: General Troubleshooting & Best Practices
MCQs
If the webcam video is lagging or dropping frames, which of the following might improve performance?
A. Increase resolution to 4K
B. Lower the frame rate
C. Use a lower resolution
D. Switch to the composite video output
Answer: C. Use a lower resolution

Short-Answer
Name two commands or methods you can use to check the CPU and memory usage on your Raspberry Pi when troubleshooting performance issues.
Answer:

top or htop

free -h

(Additionally, vcgencmd measure_temp for temperature)

Why might you need to install haveged on a headless Raspberry Pi when enabling VNC?
Answer: It provides additional entropy for secure operations (including SSH/VNC) when there’s little keyboard/mouse input, preventing entropy starvation.

Section 10: Additional Open-Ended/Discussion Questions
Explain how to configure the Raspberry Pi 400 so that it automatically logs in upon boot and starts the desktop environment (useful for kiosk-like setups).
Answer will vary. Consider using raspi-config or modifying config files to auto-login.

Discuss how changing contour area thresholds in a motion detection script affects sensitivity and false positives.
Answer will vary. Lower thresholds might detect tiny movements or noise; higher thresholds ignore small changes but may miss subtle motion.

Propose a simple Python script flow that captures an image every 30 seconds and uploads it to a cloud service.
Answer will vary. A sample approach: use a loop with time.sleep(30), capture an image (fswebcam or OpenCV), then upload via an API (AWS S3, Google Cloud, etc.).


Answer will vary. A sample approach: use a loop with time.sleep(30), capture with fswebcam or OpenCV, then upload via an API to AWS S3, Google Cloud, etc.


