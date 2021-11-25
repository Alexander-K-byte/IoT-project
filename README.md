# IoT-project
design facial recognition system with ultrasonic distance sensor interface on Raspberry pi 4b.  </br>  
(once we have working prototype, script will be uploaded)

## Concept
Tasked with coming up with unique prototype to demonstrate IoT knowledge gained during course, this is a collaboration between me (Alexander Kerr) and my class colleague, Toni Mansikka.
So facial recognition has been widely used, ultrasonic distance sensors are widely used, I am pretty sure that someone has probably implemented a similar system but as far as I can tell, there was nothing documented or widely available during our storming session for this combination.  

Breakdown of what we hope to achieve, create a facial recognition system using Raspberry Pi, Picamera, and 2 ultrasonic distance sensors.  The main idea would be to disable USB ports so that system can't be interfaced with.  Pi camera would be ideal solution since it has it's own interface which is not connected to the USB ports.  

Script can be written to perform some base action if user is unknown only allowing one or two actions from distance sensor, if user is known, script will enable USB ports, and have pre-written actions for distance sensor (open browser, terminal, perhaps play music).

## Implementation
Facial recognition will be done using openCV and facial recognition software available from https://github.com/carolinedunn/facial_recognition.  After these are installed, we then need to train our model for facial recognition.  Once we have our facial recognition up and running we will then need to import our distance sensors and write scripted actions depending on if the user is known or unknown.

## Troubleshooting to date
- 08/11/2021 Installation of openCV, with newer version of Raspberry Pi OS, libqt has become obsolete from repositories.  Initially was able to swap qt4 for qt5, but since updating OS, this is no longer an option.  Building from source now either has errors or once complete, does not install openCV correctly.
- Pip install does not include complete version of openCV, had g-streamer errors running code, PiCamera enable is not available from desktop preferences?  Enabled via raspi-config from terminal (later found out g-streamer errors may have came from broken picamera)
- After getting nowhere for a long time, we attempted downloading the older version of Raspbian, once the old repositories were ok'd we were able to build openCV with required dependencies from source.  At this point we discovered that PiCamera appears to be broken.
- 21/11/2021 Progress to date, since installing old OS we have now installed openCV, changed PiCamera to USB version so that we can build a working prototype, trained the model to recognize 2 users, added Ultrasonic distance sensor interface and configured it with some basic actions that run on specific user being identified.
