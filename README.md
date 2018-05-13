# Constellation
## Laser-Based Interactive Musical Instrument
Constellation is a muscial instrument that allows users to play different sounds through the interaction with a series of laser rays.

## Team
- Jimmy Xu
- Mark Unger
- Ryan Ong

## Summary
The device is made up of two parts: (1) a series of buzzers surrounding (2) a central control box. Each buzzer is mounted on top of a post and is connected to the box in the center. The box is made of foamboard with 10 laser diodes and an equal number of photoresistors. The diodes are placed on two adjacent sides of the box with 7 on the longer side and 3 on the shorter side and emit laser to the photoresistors that are on the opposite sides of the box. The longer side maps to 7 different notes (CDEFGAB), and the shorter side represents three octaves (3/4/5). The Featherboard reads the resistance and changes the sound (frequency, pitch, interval, etc.) of the buzzers accordingly.

## Components

### Hardware
- Adafruit Feather x 3
- Piezzo Buzzers x 3
- Laser diodes x 10
- Photoresistors x 10
- Box
- Paper cups x 9 (7 as amplifiers, 2 as controllers)

### Software
The program detects the simultaneous change in resistance of different photoresistors caused by the user blocking the paths of the lasers, and adjusts the collective frequency/harmonics of the buzzers accordingly. One featherboard reads the resistance through 10 analog pins and sends out frequencies to a buzzer. 

### Diagrams
![diagram](https://github.com/rayneong/c-p-and-e-final-project-spring-2018/blob/master/images/spec-diagram.png)

## Challenges
First, since we spent half of our time on ideating, we had limited amount of time to implement our idea. It took longer than we expected to get the components and make the box. We only had a few days left when we started to build our final product.
Also, assembling unfamiliar components was difficult. While we only needed to power the laser diodes, it was tricky to control three buzzers simultaneously. We found out that Featherboard does not support controlling multiple buzzers natively, and we could not find a working library. Therefore, we had to use 3 Featherboards with each one controlling a buzzer. As a result, it took us a whole day to build the circuit and debug (there were around 100 wires).

## Timeline
- Week 1: Ideation.
- Week 2: More ideation.
- Week 3: Prototype built. Components ordered. Started to write the control program.
- Week 4: Continued to write the control program. Individual testing on how each component worked. Started to design the box.
- Week 5: Built the box. Integrated everything together. Final testing. Presentation.

## Gallery
### Proof of Concept
![prototype-A](https://github.com/rayneong/c-p-and-e-final-project-spring-2018/blob/master/images/IMG_0548.JPG)
![prototype-B](https://github.com/rayneong/c-p-and-e-final-project-spring-2018/blob/master/images/IMG_0788.JPG)
### Input Planning
![function-planning](https://github.com/rayneong/c-p-and-e-final-project-spring-2018/blob/master/images/IMG_0550.JPG)
![function-planning-2](https://github.com/rayneong/c-p-and-e-final-project-spring-2018/blob/master/images/IMG_0788.JPG?raw=true)
### Building
![building-A](https://github.com/rayneong/c-p-and-e-final-project-spring-2018/blob/master/images/IMG_0559.JPG)
![building-B](https://github.com/rayneong/c-p-and-e-final-project-spring-2018/blob/master/images/IMG_0560.JPG)
![building-C](https://github.com/rayneong/c-p-and-e-final-project-spring-2018/blob/master/images/IMG_0561.JPG)
![building-D](https://github.com/rayneong/c-p-and-e-final-project-spring-2018/blob/master/images/IMG_0562.JPG)
![final-build](https://github.com/rayneong/c-p-and-e-final-project-spring-2018/blob/master/images/IMG_0567.JPG)
### Info Sheet
![info-sheet](https://github.com/rayneong/c-p-and-e-final-project-spring-2018/blob/master/images/info_sheet_print.jpg)
### Demo
<iframe width="560" height="315" src="https://www.youtube.com/embed/oNOQ-uCfrFw" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
