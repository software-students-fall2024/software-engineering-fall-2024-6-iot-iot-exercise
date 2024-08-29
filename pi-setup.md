# Set up the Raspberry Pi

## Headless setup

You will need to set up the Raspberry Pi without a monitor, keyboard, or mouse (i.e. a **headless** setup). This requires setting up the Pi's operating system to enable `ssh` remote login from another computer on the network. A Raspberry Pi that is already set in this way may [or may not] be provided for you by the instructor, but you should be familiar with it regardless.

The instructions in this video outline the basic headless setup: [Headless Raspberry Pi Setup (New Simpler/Easier Method) - Without Monitor, Keyboard/Mouse](https://www.youtube.com/watch?v=u8bbp79haN4), with the following notes:

- If you want to be able to use the Pi's Graphical User Interface (GUI), make sure to install the full operating system (not the Lite version) and after setup is complete, see [this video](https://www.youtube.com/watch?v=9fEnvDgxwbI) for how to use VNC remote desktop to access it.
- Set the hostname to `pi_team_<team number>.local`, e.g. `pi_team_4.local` if you are on team #4.
- Set the username to `pi`.
- Set the password to `<team number>_team_pi`, e.g. `4_team_pi` if you are on team #4.
- If possible, create a wifi hotspot on your phone and configure the wireless LAN to connect to that. Alternatively, it _may_ be possible to connect the device to an NYU wifi network using a student's NYU credentials. Set the WiFi country to `US`.
- If using Windows, note that either Windows 10 Terminal or Git Bash or Windows Subsystem for Linux (WSL) are recommended for running the `ssh` command, rather than using the PuTTY application.
- Once the Pi is set up, you can verify that it is online with `ping pi_team_<team number> -n 1` (if a response arrives, it's online!) and connect to it using `ssh pi@pi_team_<team number>` from the command line.

## Useful resources

The Raspberry Pi is a powerful computer that has many capabilities for integrating both software and hardware. A few tutorials that might be of interest:

- [Raspberry Pi Documentation: Camera](https://www.raspberrypi.com/documentation/accessories/camera.html)
- [How to use Arducam OV5647 Camera Module for Raspberry Pi](https://www.youtube.com/watch?v=ZZmvfTklReA)
- [Take Pictures and Videos with the picamera Python Library](https://roboticsbackend.com/raspberry-pi-camera-picamera-python-library/)
- [Recording Audio on the Raspberry Pi with Python and a USB Microphone](https://makersportal.com/blog/2018/8/23/recording-audio-on-the-raspberry-pi-with-python-and-a-usb-microphone)
- [Real Time Inference on Raspbery Pi 4 (using PyTorch and OpenCV)](https://pytorch.org/tutorials/intermediate/realtime_rpi.html)
- [Build a smart IoT device with TensorFlow Lite and Raspberry Pi](https://www.youtube.com/watch?v=Lyh84KMqUPI)
- [Turn your Raspberry Pi into a Wifi Router](https://www.youtube.com/watch?v=laeOmNDE-Ac)
- [Kookye Smart Home Sensor Tutorials](https://kookye.com/2016/08/01/smart-home-sensor-kit-for-arduinoraspberry-pi/)
- [Raspberry Pi GPIO Pinout](https://projects-raspberry.com/raspberry-pi-4-pinout/)
