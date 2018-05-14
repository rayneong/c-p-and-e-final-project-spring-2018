# Constellation
## Laser-Based Interactive Musical Instrument
Constellation is a muscial instrument that allows users to play different sounds through the interaction with a series of laser rays.

## Team
- Jimmy Xu
- Mark Unger
- Ryan Ong

## Summary
The device is made up of two parts: (1) a series of buzzers surrounding (2) a central control box. Each buzzer is mounted on top of a post and is connected to the box in the center. The box is made of foamboard with 10 laser diodes and an equal number of photoresistors. The diodes are placed on two adjacent sides of the box with 7 on the longer side and 3 on the shorter side and emit laser to the photoresistors that are on the opposite sides of the box. The longer side maps to 7 different notes (CDEFGAB), and the shorter side represents three octaves (2/3/4). The Featherboard reads the resistance and changes the sound (frequency, pitch, interval, etc.) of the buzzers accordingly. Each Featherboard manages a unique harmonic of the desired note, culminating in a more unique sound and timbre. If multiple notes are triggered simultaneously, the machine will play an arpeggio of notes in ascending order.

## Components

### Hardware
- Adafruit Feather x 3
- Piezzo Buzzers x 3
- Laser diodes x 10
- Photoresistors x 10
- Box
- Paper cups x 9 (7 as amplifiers, 2 as controllers)
- Electrical Tape

### Software
The program detects the simultaneous change in resistance of different photoresistors caused by the user blocking the paths of the lasers, and adjusts the collective frequency/harmonics of the buzzers accordingly. Each featherboard reads the resistance through 10 analog pins and sends out the desired frequencies to a buzzer. 

During the development of the project, support for harmonic overtones was added such that each featherboard would handle a unique harmonic for the desired note. To add synthesizer-like functionality, an array structure was added to store and support arpeggios. When multiple notes were triggered simultaneously, the featherboards would play an arpeggio of ascending notes.

### Diagrams
![diagram](https://github.com/rayneong/c-p-and-e-final-project-spring-2018/blob/master/images/spec-diagram.png)

## Challenges
First, since we spent half of our time on ideating, we had a limited amount of time to implement our idea. It took longer than we expected to get the components and make the box. Our first shipment of lasers, from Amazon, was an empty bag with a gaping tear on the top. We had to wait for a reshipment of the lasers, and thus we spent more time on fleshing out the concept and only had a few days left when we started to build our final product.

Building the control box required cutting precision and a purchase of a hot-glue gun, as the standard glue was not able to sufficiently hold the standing walls in-place. It was difficult to create holes that were exactly big enough for the lasers and photoresistors to sit in (and avoid angles), and eventually chopsticks were found to coincidentally be a good match for poking holes. Aligning the lasers to directly line-up with and hit their corresponding photoresistor required an incredible amount of patience for trial-and-errors.

Also, assembling unfamiliar components was difficult. While we only needed to power the laser diodes, it was tricky to control three buzzers simultaneously. During prototype, we found out that Featherboards do not support simultaneous control of multiple buzzers natively, and we could not find a working library. After exploring options including a slave-master-relay configuration, we decided to use 3 Featherboards that shared the output signals from the photoresistors, with each one controlling a buzzer. As a result, it took one day to build the circuit, and another day to debug (there were around 100 wires). Plenty of wires were cut and stripped, and plenty of thumbs and teeth were sore in the process of doing so. 

It was absolutely terrifying when some of the analog inputs did not print an expected value, as we had a heap of wires and thought of testing each one was terrifying. Luckily, the issue was quickly whittled down to the insecure electrical taping used to connect the wires and photoresistors. Once that was resolved, the piezzo buzzers played what could be best described as a pulsing noise, rather than the desired smooth tone. The delay rate of the code had to be iteratively tuned and reuploaded to the three featherboards separately, until the sound was to our satisfaction. 

## Timeline
- Week 1: Ideation.
- Week 2: More ideation.
- Week 3: Prototype built. Components ordered. Started to write the control program.
- Week 4: Continued to write the control program. Individual testing on how each component worked. Started to design the box.
- Week 5: Built the box. Integrated everything together. Final testing. Presentation.

## Gallery
### Demo
https://youtu.be/oNOQ-uCfrFw
### Proof of Concept
![prototype-A](https://github.com/rayneong/c-p-and-e-final-project-spring-2018/blob/master/images/IMG_0548.JPG)
### Input Planning
![prototype-B](https://github.com/rayneong/c-p-and-e-final-project-spring-2018/blob/master/images/IMG_0788.JPG)
### Building
![building-A](https://github.com/rayneong/c-p-and-e-final-project-spring-2018/blob/master/images/IMG_0559.JPG)
![building-B](https://github.com/rayneong/c-p-and-e-final-project-spring-2018/blob/master/images/IMG_0560.JPG)
![building-C](https://github.com/rayneong/c-p-and-e-final-project-spring-2018/blob/master/images/IMG_0561.JPG)
![building-D](https://github.com/rayneong/c-p-and-e-final-project-spring-2018/blob/master/images/IMG_0562.JPG)
![final-build](https://github.com/rayneong/c-p-and-e-final-project-spring-2018/blob/master/images/IMG_0567.JPG)
### Info Sheet
![info-sheet](https://github.com/rayneong/c-p-and-e-final-project-spring-2018/blob/master/images/info_sheet_print.jpg)

## Reference
https://learn.adafruit.com/adafruit-feather-32u4-basic-proto/pinouts

http://www.sengpielaudio.com/calculator-harmonics.htm

https://www.sfmoma.org/publication/soundtracks/rafael-lozano-hemmer/ [see 'sphere-packing']
