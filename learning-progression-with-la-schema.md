# CPE 1040 - Fall 2020

This is learning progression 004 for the Fall 2020 installment of the course CPE 1040: Introduction to Computer Engineering at MSU Denver.

<img src="images/lp004-img.jpg" width="800" />

Table of Contents
=================

* [CPE 1040 \- Fall 2020](#cpe-1040---fall-2020)
  * [Learning Progression 004: External LEDs](#learning-progression-004-external-leds)
  * [Lab kit](#lab-kit)
    * [Parts for progression](#parts-for-progression)
  * [Steps](#steps)
    * [Step 6: Electromagnetism](#step-6-electromagnetism)
      * [1\. Study](#1-study)
        * [Fundamental interaction](#fundamental-interaction)
        * [Electrostatics &amp; magenetostatics](#electrostatics--magenetostatics)
        * [Theories of electromagnetism](#theories-of-electromagnetism)
        * [Charge, voltage, and current](#charge-voltage-and-current)
        * [Resistance](#resistance)
        * [Ohm's law](#ohms-law)
        * [Power](#power)
      * [2\. Apply](#2-apply)
      * [3\. Present](#3-present)
    * [Step 7: Circuits &amp; circuit elements](#step-7-circuits--circuit-elements)
      * [1\. Study](#1-study-1)
        * [Circuits](#circuits)
        * [Short circuit](#short-circuit)
        * [Circuit elements](#circuit-elements)
        * [Resistors in series and in parallel](#resistors-in-series-and-in-parallel)
      * [2\. Apply](#2-apply-1)
      * [3\. Present](#3-present-1)
    * [Step 8: Multimeter](#step-8-multimeter)
      * [1\. Study](#1-study-2)
        * [Measuring voltage](#measuring-voltage)
        * [Different grounds](#different-grounds)
        * [Measuring current](#measuring-current)
        * [Measuring resistance](#measuring-resistance)
        * [Checking for continuity](#checking-for-continuity)
      * [2\. Apply](#2-apply-2)
      * [3\. Present](#3-present-2)
    * [Step 9: Basic LED circuit](#step-9-basic-led-circuit)
      * [1\. Study](#1-study-3)
      * [2\. Apply](#2-apply-3)
      * [3\. Present](#3-present-3)
    * [Step 10: micro:bit breakout board](#step-10-microbit-breakout-board)
      * [1\. Study](#1-study-4)
      * [2\. Apply](#2-apply-4)
      * [3\. Present](#3-present-4)
    * [Step 11: micro:bit GPIO pins](#step-11-microbit-gpio-pins)
      * [1\. Study](#1-study-5)
        * [micro:bit I/O](#microbit-io)
        * [Digital vs analog](#digital-vs-analog)
      * [2\. Apply](#2-apply-5)
      * [3\. Present](#3-present-5)
    * [Step 12: Screensaver extension](#step-12-screensaver-extension)
      * [1\. Study](#1-study-6)
        * [Extending a program](#extending-a-program)
        * [Defining extra rows](#defining-extra-rows)
        * [Choice of pins](#choice-of-pins)
      * [2\. Apply](#2-apply-6)
      * [3\. Present](#3-present-6)

## Learning Progression 004: External LEDs
[[toc](#table-of-contents)]  

This progression introduces fundamentals of computing, including the binary system of data representation as well as the basics of memory and processing. We introduce assembly language in the context of a minimal instruction set processor. This is where the lowest layer of the software stack and the highest layer of the hardware stack coexist, and where user programs are translated into machine code and executed by the processor one instruction at a time. This is also the level of computing which directly correpsonds to the simplest theoretical models of a computer. We also introduce the input-output capabilities of the micro:bit and build an external circuit to serve as an extension to the built-in 5x5 LED matrix to run our Screensavers program on.

## Lab kit
[[toc](#table-of-contents)]  

The lab kit is described in detail in a [separate page](lab-kit.md). Please, make sure you read the care and safety instructions embedded for most of the kit components.    

### Parts for progression  
[[toc](#table-of-contents)]  

1. Breadboard.  
2. Breadboard power supply with wall plug.  
3. micro:bit breakout board (connector).  
4. 330 Ohm resistor (10 count).  
5. LEDs (10 count).  
6. Wires.  
7. Multimeter with needle-tipped probes.  

## Steps
[[toc](#table-of-contents)]  

### Step 6: Electromagnetism
[[toc](#table-of-contents)]  

#### 1. Study
[[toc](#table-of-contents)]  

##### Fundamental interaction
[[toc](#table-of-contents)]  

`[<lernact-rd>]`_Electromagnetism_ is one of the four [fundamental interactions (or `[<cept>]`_forces_)](https://en.wikipedia.org/wiki/Fundamental_interaction) in Nature humanity is currently aware of. We have developed theories to explain it but they are still in development. Even a short survey of our understanding of electromagnetism is beyond the scope of this learning progression.

##### Electrostatics & magenetostatics
[[toc](#table-of-contents)]  

Humanity encountered electromagnetism thousands of years ago, largely in the form of `[<cept>]`_electrostatic_ and `[<cept>]`_electromagnetic_ phenomena in the world around. If you have ever combed your hair and it stood up, or small bits of paper were attracted to the comb afterwards, or walked with woolen socks on the carpet and, when you tried to turn the light on, a small spark jumped from your finger to the switch, you have also encountered one of these phenomena.

Thousands of years later, human science has advanced enough to know that electricity and magnetism are manifestations of the same fundamental physical phenomenon, and, of course, that the most visible example of all is `[<cept>]`_light_.

##### Theories of electromagnetism
[[toc](#table-of-contents)]  

Here is a list of three electromagnetic theories:
1. Flow of charge through conductors. This is not a full theory, but it is the first that students encounter in their studies due to the simplicity and approachability of the `[<cept>]`[_hydraulic analogy_](https://en.wikipedia.org/wiki/Fundamental_interaction), linking the largely invisible phenomenon of electric current in wires to the familiar flow of water through pipes. The hydraulic analogy quickly fails when we dig deeper, so it is used largely as a first bridge from the familar to the infamiliar.    
2. Maxwell's equations. This is the most complete theory of electromagnetism that does not involve `[<cept>]`_quantum mechanics_ and is a sufficient basis for electric and computer technology. It masterfully weaves electric and magnetic fields together into an elegant mutual interdependence and explains current as electromagnetic waves flowing _outside_ the wires rather than inside.  
3. Quantum electrodynamics. This is the current pinnacle of electromagnetic theory, which is consistent with the theory of `[<cept>]`_special relativity_ and is on track to unify electromagnetism with the `[<cept>]`_weak interaction_. As the name suggests, it is fully immersed in quantum mechanics, and sprung about, as usual, when scientists dug deeper and encountered phenomena that could not be explained with current theory.    

##### Charge, voltage, and current
[[toc](#table-of-contents)]  

The hudraulic analogy will be sufficient to motivate the necessary concepts that will lead us to hands-on application in a couple of steps.

Computer technology is built on the phenomenon of `[<cept>]`_electricity_, which is understood to be a flow of `[<cept>]`_charge_. Charge is a fundamental property of matter, and there are two types, conventionally called `[<cept>]`_positive_ and `[<cept>]`_negative_. `[<cept>]`_Atoms_ are the fundamental building blocks of matter and consist of positively-charged `[<cept>]`_nuclei_ and negatively-charged `[<cept>]`_electrons_, circling around the nuclei. When the electrons are close to the nucleus, the atom is electrically `[<cept>]`_neutral_, but when they are pulled away from the nucleus, an `[<cept>]`_electric field_ arises that attracts them together. So, charges interact, with like charges repelling each other, and opposite charges attracting each other.

When an electric field causes a directed motion of significant number of electons, we observe what is known as electrical `[<cept>]`_current_. Conceptually, electricity is the flow of electrons through wires. `[<cept>]`_Voltage_ is a measure of the energy required to create current between two points in a `[<cept>]`_conducting_ wire. It can also be thought as the magnitude of the electric field causing electrons to move.

##### Resistance  
[[toc](#table-of-contents)]  

Not all matter conducts current as well as wires, which are usually drawn from metals. Some materials do not conduct electricity at all. To characterize this important difference, we call this property `[<cept>]`_resistance_ and study what it depends upon. In metals, electrons from the outer `[<cept>]`_atomic orbitals_ are easy to dislodge and set to move about the material freely. When a voltage is applied through the material, these electrons move in the same direction, creating current.

The full understanding of [resistance](https://en.wikipedia.org/wiki/Electrical_resistance_and_conductance) quickly moves into the quantum realm, but a simplified explanation, based on `[<cept>]`[_band theory_](https://en.wikipedia.org/wiki/Electrical_resistivity_and_conductivity#Band_theory_simplified) can still be given. Electrons around atomic nuclei can only take discrete `[<cept>]`_states_, called bands. Moving from one band to another takes `[<cept>]`_discrete_ amounts of energy. Different materials have a different configuration of bands around their nuclei, and correspondingly more or less easy transition of electrons from one band to another. In conductors, moving from one band to another is easy. In other materials, it is more difficult or impossible, and these materials are correspondingly called `[<cept>]`_dielectrics_ (aka `[<cept>]`_insulators_).  

##### Ohm's law
[[toc](#table-of-contents)]  

There is an elegant relation between voltage (the measure of the energy necessary to create current), the magnitude of the current, and the amount of resistance of the material conducting the current. It is called Ohm's law. If we designate voltage as capital V, current as capital I, and resistance as capital R, the equation of Ohm's law is just

V = IR

These are all measurable quantities and their units are Volts (for voltage), Amperes (for current), and Ohms (for resistance). Naturally, these are the names of 3 of the most prominent scientists who contributed to the theory which underlies electricity and, later, computers.  

##### Power
[[toc](#table-of-contents)]  

A most important quantity for the energy required to conduct current is `[<cept>]`_power (P)_, and it also has a very elegant equation:

P = VI

#### 2. Apply
[[toc](#table-of-contents)]  

1. `[<lernact-disc>]`What if our physical world had 3 different charges instead of 2 (positive and negative)?  
2. `[<lernact-disc>]`Each fundamental interaction has a mediator particle. What is the particle for Electromagnetism? How can you explain that?      
3. `[<lernact-disc>]`Einsein's largest contribution to science were his theories of relativity, special and general. But he did not get his Nobel Prize in Physics for either one. What did Einstein get a Nobel Prize for?    
4. `[<lernact-disc>]`**[Optional challenge, max 10 extra step points]** Discuss the details of the hydraulic analogy for current, and find one point where it breaks (that is, the analogy stops holding).  

#### 3. Present
[[toc](#table-of-contents)]  

In the [Lab Notebook](README.md):

1. Show your work for 6.2.1 in well-formatted Markdown, including whatever images, tables, or other graphical elements you find necessary.  
2. Show your work for 6.2.2 in well-formatted Markdown, including whatever images, tables, or other graphical elements you find necessary.  
3. Show your work for 6.2.3 in well-formatted Markdown, including whatever images, tables, or other graphical elements you find necessary.  
4. Show your work for 6.2.4 in well-formatted Markdown, including whatever images, tables, or other graphical elements you find necessary.  


### Step 7: Circuits & circuit elements  
[[toc](#table-of-contents)]  

#### 1. Study
[[toc](#table-of-contents)]  

##### Circuits  
[[toc](#table-of-contents)]  

Circuits are closed loops of wires and various `[<cept>]`_circuit elements_, in which electricity flows to do useful work. All computers are large (collections of) circuits. One of the best ways to conceptualize what a circuit is is to study `[<cept>]`[_Kirchhoff's circuit laws_](https://en.wikipedia.org/wiki/Kirchhoff%27s_circuit_laws):  
1. The law for voltage states that around every closed loop in a circuit the sum of the voltages of all circuit segments that compose the loop is zero. Voltage is a relative quantity, so it is always measured between two points. So, every segment of a loop has a voltage between its terminals. Voltage is positive at a point A if it is higher than the voltage at a reference point B. The universal convention for reference is `[<cept>]`_ground (0 Volts)_, but for a segment in the loop, that doesn't have to be the case. When a voltage increases across a segment (e.g. because it contains a battery) the volgate is said to `[<cept>]`_rise_. When the voltage decreases across a segment (e.g. because there is an element with strong resistance, which requires a lot of voltage to get charge to move across it) the voltage is said to `[<cept>]`_drop_. The voltage law states that around a closed loop, the volgate rises and drops sum up to 0. _Note that this zero has no units, so it should not be read as 0 Volts (or O V)._   
2. The law for current states that the sum of all currents in any junction in a circuit is zero. Current is an absolute quantity, because it measures the amount of charge is traveling along a conducting segment of a circuit in a certain direction. Points in the circuit where wires and circuit elements meet, are called junctions. Naturally, if the currents flowing in and those flowing out of a junction didn't cancel out, there would be a build-up of charge at the point of the junction. Remember that like charges repel, so the build-up of charge will eventually cause the current to stop, and that would be a most useless circuit.  

##### Short circuit
[[toc](#table-of-contents)]  

The common term `[<cept>]`_short circuit_ refers to a closed loop that has a voltage rise but doesn't have a resistive element to counterbalance with a voltage drop. This can only occur instantaneously and usually destroys the circuit (e.g. by burning the wire or destroying the battery).  

##### Circuit elements  
[[toc](#table-of-contents)]  

Circuit elements are devices which alter the voltage and current of (segments of) the circuit they are connected in. `[<cept>]`_Passive_ elements employ simple electromagnetic phenomena to do so:
1. A `[<cept>]`[_resistor_](https://en.wikipedia.org/wiki/Resistor), a 2-terminal element, provides resistance and drops the voltage between its terminals according to Ohm's law.  
2. A `[<cept>]`[_capacitor_](https://en.wikipedia.org/wiki/Capacitor), a 2-terminal element, acts like a small store of charge (meaning a very-low capacity battery). It is said to `[<cept>]`_charge_ (accumulate charge) and `[<cept>]`_discharge_ (dissipate charge).  
3. An `[<cept>]`[_inductor_](https://en.wikipedia.org/wiki/Inductor), a 2-terminal element, and is usually some sort of coil, opposes the flow of current by aligning the magnetic field that the current creates in opposition to the current.  

Active elements employ more complex electromagnetic phenomena (due to their special engineered structure and composition):
1. A `[<cept>]`[_diode_](https://en.wikipedia.org/wiki/Diode), a 2-terminal `[<cept>]`_semiconductor_ device, conducts current only in one direction and stops it in the opposite direction.  
   1. A `[<cept>]`[_light-emitting diode (LED)_](https://en.wikipedia.org/wiki/Light-emitting_diode), a 2-terminal element, is a diode which emits light when it conducts electricity.  
2. A `[<cept>]`[_transistor_](), a 3-terminal semiconductor device, acts as an `[<cept>]`_electronic switch_ in which one of the terminals (called the `[<cept>]`_base_ or `[<cept>]`_gate_, depending on the type of transistor) controls the flow of current across the other two terminals (called, correspondingly, `[<cept>]`_emitter_ and `[<cept>]`_collector_, and `[<cept>]`_source_ and `[<cept>]`_drain_).  

Other elements:
1. Voltage and current sources drive the circuit.  
2. Wires, which connect all other elements into closed loops, generally do not alter the voltage or current significantly at normal scales.  
3. Mechanical switches (as opposed to transistors) provide controllable breaks in the circuit.  

##### Resistors in series and in parallel
[[toc](#table-of-contents)]  

Resistors can be connected in various configurations, but they are generally composed of two basic configurations:
1. `[<cept>]`_Series_ (aka "in-series") describes two resistors sharing a terminal:
   ```
                        -----------                    -----------
           ------------|     R1    |------------------|     R2    |-------------
                        -----------                    -----------
   ```
2. `[<cept>]`_Parallel_ (aka "in-parallel") described two resistors sharing both their terminals:
   ```
                        -----------          
                 /-----|     R1    |-----\
                 |      -----------      |    
           ------|                       |------ 
                 |      -----------      |    
                 \-----|     R1    |-----/
                        -----------          
   ```

`[<lernact-ans>]`**Question 7.1.1:** In a series configuration of resistors, what (current or voltage) is the same? _Hint: Use Ohm's and Kirchhoff's laws._  
`[<lernact-ans>]`**Question 7.1.2:** In a parallel configuration of resistors, what (current or voltage) is the same? _Hint: Use Ohm's and Kirchhoff's laws._    

#### 2. Apply
[[toc](#table-of-contents)]  

1. `[<lernact-prac>]`Take a look at the following sketch:

   <img src="images/simple-circuit.jpg" width="400" />

   It contains a simple circuit: a 3.3V voltage source (power supply) and a resistor configuration. The configuration can be a single resistor, two resistors in series or two resistors in parallel (both configurations are shown in the sketch below the circuit). Use Ohm's Law (V = IR) to calculate (i) the voltages across all resistors, (ii) the currents through all resistors, and (iii) the value of R, in each of the following cases:
   1. R = 330 Ohms.  
   2. R = 10 kOhms.  
   3. R = R1 + R2 = 330 Ohms + 330 Ohms.  
   4. R = R1 + R2 = 10 kOhms + 10 kOhms.  
   5. R = R1 + R2 = 330 Ohms + 10 kOhms.  
   6. R = R1 || R2 = 330 Ohms || 330 Ohms.  
   7. R = R1 || R2 = 10 kOhms || 10 kOhms.  
   8. R = R1 || R2 = 330 Ohms || 10 kOhms.  

2. `[<lernact-prac>]`**[Optional challenge, max 5 step points]** Using the [CircuitJS](http://lushprojects.com/circuitjs/circuitjs.html) in-browser circuit drawer and simulator, build the following circuit:

   <img src="images/circuit-js-task-circuit.png" width="600" />

   1. Note the alternative symbol for a volgate source (or battery):
      ```
         |   +
      -------
        ---
         |   -
      ```
   2. If there are any elements on the screen, remove them by selecting them and deleting.  
   3. Under draw, find the elements of the circuit (Voltage source, resistor, switch, wires).  
   4. Right-click on the voltage source and create a slider from 0 to 5V. It will appear in the right column.  
   5. Right-click on the resistor and select **Show in scope**.
   6. Disconnect the switch, then reconnect.  
   7. Vary the volgate from the slider.  

3. `[<lernact-prac>]`**[Optional challenge, max 10 step points]** Using the [CircuitJS](http://lushprojects.com/circuitjs/circuitjs.html), build the following circuit, simulate it, and explain its general operation. _Hint: It is a simple dampened oscillator._

   <img src="images/circuit-js.png" width="400" />

#### 3. Present
[[toc](#table-of-contents)]  

In the [Lab Notebook](README.md):

1. Answer question 7.1.1. 
2. Answer question 7.1.2. 
3. Draw the circuit and show the calculations for case 7.2.1.1.  
4. Draw the circuit and show the calculations for case 7.2.1.2.  
5. Draw the circuit and show the calculations for case 7.2.1.3.  
6. Draw the circuit and show the calculations for case 7.2.1.4.  
7. Draw the circuit and show the calculations for case 7.2.1.5.  
8. Draw the circuit and show the calculations for case 7.2.1.6.  
9. Draw the circuit and show the calculations for case 7.2.1.7.  
10. Draw the circuit and show the calculations for case 7.2.1.8.  
11. Record a video (in the simulator) of the operation of the circuit for 7.2.2.  
12. Record a video (in the simulator) of the operation of the circuit for 7.2.3, and include a narrative with explanation and analysis of its operation.    


### Step 8: Multimeter  
[[toc](#table-of-contents)]  

#### 1. Study
[[toc](#table-of-contents)]  

`[<lernact-rd>]`Our lab kit contains a sparkfun-branded `[<cept>]`[_multimeter_](https://github.com/ivogeorg/ce-learning-progression-004-06-12/blob/master/lab-kit.md#2-multimeter), a device capable of `[<cept>]`_measuring_ (meaning assigning numerical values to) electrical quantities. The [sparkfun multimeter tutorial](https://learn.sparkfun.com/tutorials/how-to-use-a-multimeter) is an excelent material that is difficult to top.  

Note that the units of measurement are from the [International System of Units](https://en.wikipedia.org/wiki/International_System_of_Units).  In particular, note the section on [prefixes](https://en.wikipedia.org/wiki/International_System_of_Units#Prefixes), which indicate the scale of the units. The multimeter has several scale settings for each measurable quantity and the choice of setting is important for the proper [care](https://github.com/ivogeorg/ce-learning-progression-004-06-12/blob/master/lab-kit.md#care-1) of the instrument.  

##### Measuring voltage  
[[toc](#table-of-contents)]  

Voltage is a measure of the difference in potential energy for the moving of electrical charge. Voltage is a `[<cept>]`_relative_ quantity, that is, we cannot the voltage of at any point in an electrical circuit without having a `[<cept>]`_reference point_. The units of measure of voltage (V) are `[<cept>]`_Volts (V)_. The reference point is usually assumed to be 0 V `[<cept>]`_ground_. Why is that? The ground of the Earth is assumed to be an infinite source or sink of electrical charge, so any point in an electrical cirtuit which is connected to the ground through a conducting wire will lose its voltage relative to it. Therefore, this is an ideal global reference point.

Voltage is measured between two points in a circuit. To measure voltage:
1. Put the multimeter (with the battery installed) dial in one of the voltage measurement positions. In this progression we will only deal with constant voltage, indicated by the symbol:  
   ```
   V ---
     ...
   ```
   The setting should be equal to or exceed the maximum value you are going to measure. For the micro:bit, which operates at 3.3V maximum voltage, the dial of our multimeter should be set to 20 V.  
2. Connect the two probes, the black one to the middle (common) port, and the red one to the port on the right. The needle-tipped probes can reach into breadboard holes.  
3. Touch the black probe to ground.  
4. Touch the red one to the point in the circuit you want to measure the voltage.  
5. Read off the value (in Volts).  

##### Different grounds
[[toc](#table-of-contents)]  

You need to make sure that you measure voltages at points in a circuit **relative to its designated ground**. Voltage values measure against the ground of a different (not directly connected) circuit are meaningless.

`[<lernact-ans>]`**Question 8.1.1:** What is the voltage you measure between the GND and 3V3 pins of the micro:bit?   
`[<lernact-ans>]`**Question 8.1.2:** What is the voltage you measure between the GND and VCC pins of the power supply?   
`[<lernact-ans>]`**Question 8.1.3:** What is the voltage you measure between the GND pin of the micro:bit and the and VCC pin of the power supply?   
`[<lernact-ans>]`**Question 8.1.4:** What is the voltage you measure between the GND pin of the power supply and the 3V3 pin of the micro:bit?   

##### Measuring current  
[[toc](#table-of-contents)]  

Current is a measure of charge traveling through a section of a circuit (be it a wire or a circuit element). Current is an `[<cept>]`_absolute_ quantity, that is, we do not need a reference point. The units of measure for current (I) are `[<cept>]`_Amperes (A)_. To measure the current flowing through a part of a circuit, we need to connect the multimeter in such a way as to have the same current flow through it as well. 

Current is measured by making the multimeter has to become "a part of" the circuit.  
1. Put the multimeter (with the battery installed) dial in one of the current measurement positions. Current settings are indicated by the symbol:  
   ```
   A ---
     ...
   ```
   The setting should be equal to or exceed the maximum value you are going to measure. For the [micro:bit](https://tech.microbit.org/hardware/1-5-revision/), the maximum current over the USB cable is 120mA and the maximum current supplied by the edge connector is 90mA.    
2. Select a point in the circuit through which the current that you want to measure flows, and break the circuit there.  
3. Connect the multimeter's probes to the two terminals of the break. The red-to-black direction should coincide with the direction of the current. (Otherwise, you will get the same value but with a negative sign in front.)  
4. Read the value (in Amperes).  

##### Measuring resistance
[[toc](#table-of-contents)]  

Resistance is the measure of opposition to the flow of electrical current through a circuit element or wire. Resistance is an absolute value. It depends only on the material and the shape of the element measured. The units of measurement are Ohms (<img src="https://render.githubusercontent.com/render/math?math=\Omega">). 

To measure resistance across a circuit element:
1. Disconnect the element and/or turn the circuit off (disconnect the power supply, battery, or other voltage or current source).  
2. Put the multimeter (with the battery installed) dial in one of the resistance measurement positions. Current settings are indicated by the symbol <img src="https://render.githubusercontent.com/render/math?math=\Omega"> (large Greek Omega). The setting should be equal to or exceed the maximum value you are going to measure. In the lab kit, we have 330<img src="https://render.githubusercontent.com/render/math?math=\Omega"> and 10<img src="https://render.githubusercontent.com/render/math?math=k\Omega"> resistors. To measure them, use the 2<img src="https://render.githubusercontent.com/render/math?math=k\Omega"> and 20<img src="https://render.githubusercontent.com/render/math?math=k\Omega"> settings, respectively.       

##### Checking for continuity  
[[toc](#table-of-contents)]  

The continuity setting is a resistance measure which emits a sound if the resistance is under a few Ohms. This means that the two points which are probed are electrically connected (as if by a wire). The symbol on the multimeter dial is:

<img src="images/multimeter-continuity-setting.jpg" width="200"/>

#### 2. Apply
[[toc](#table-of-contents)]  

1. `[<lernact-prac>]`For each of the circuits in 7.2.1, measure the voltage, current, and resistance across R. Do they match your calculations?  

#### 3. Present
[[toc](#table-of-contents)]  

In the [Lab Notebook](README.md) and the [images](images) directory:

1. Build the circuit from 7.2.1.1, embed a picture of it, and include your measurements.    
2. Build the circuit from 7.2.1.2, embed a picture of it, and include your measurements.    
3. Build the circuit from 7.2.1.3, embed a picture of it, and include your measurements.    
4. Build the circuit from 7.2.1.4, embed a picture of it, and include your measurements.    
5. Build the circuit from 7.2.1.5, embed a picture of it, and include your measurements.    
6. Build the circuit from 7.2.1.6, embed a picture of it, and include your measurements.    
7. Build the circuit from 7.2.1.7, embed a picture of it, and include your measurements.    
8. Build the circuit from 7.2.1.8, embed a picture of it, and include your measurements.    


### Step 9: Basic LED circuit  
[[toc](#table-of-contents)]  

#### 1. Study
[[toc](#table-of-contents)]  

Using LEDs in our circuits is the simplest way to build intuition about the operation of the otherwise invisible phenomena. We are going to use the following simple LED circuit for the rest of the progression:
```        
       ---------   Vcc = 3.3V                             ^^
           |                                             //
           |                330 Ohms                    //
           |            -----------                   |\ |
           |-----------|     R1    |------------------| >|------------|
                        -----------                 + |/ | -          |
                                                                      |
                                                                   -------   GND (0V)
                                                                    -----
                                                                     ---
                                                                      -
```
Notice the following:
1. The LED is a diode, so it has to be connected correctly in the right direction (longer leg toward Vcc). Reversing the `[<cept>]`_polarity_ may damage the device.  
2. There is an in-series resistor on one side before the LED. It limits the current flowing through the circuit (and, naturally, the LED) and protects it from excessive current. Connecting the LED directly between Vcc and GND may damage the device.  

#### 2. Apply
[[toc](#table-of-contents)]  

**TODO: Measure and calculate the LED circuit. Learn the breadboard.**
1. `[<lernact-prac>]`Build the LED circiut and:
   1. Measure the voltage drop across R1 and the LED. Is it within the range indicated for this color LED in the little documentation sheet in the LED pack?  
   2. Measure the current flowing through the circuit.   
   3. Using Ohm's law, calculate the `[<cept>]`_effective resistance_ R<sub>LED</sub> of the LED.  
2. `[<lernact-prac>]`Switch the power supply to 5V and repeat the work from 9.2.1.  

#### 3. Present
[[toc](#table-of-contents)]  

In the [Lab Notebook](README.md) and the [images](images) directory:

1. Build the circuit from 9.2.1, embed a picture of it, and include your measurements.    
2. Build the circuit from 9.2.2, embed a picture of it, and include your measurements.    


### Step 10: micro:bit breakout board
[[toc](#table-of-contents)]  

#### 1. Study
[[toc](#table-of-contents)]  

Read through the [micro:bit breakout hookup guide](https://learn.sparkfun.com/tutorials/microbit-breakout-board-hookup-guide) and connect your micro:bit to the breadboard. 

Note: 
1. Do not operate the micro:bit with the power supply on.  
2. Do not use the power supply ground.  
3. Use the micro:bit ground (GND) pin.  
4. The guide shows the use of a 3-color (RGB) LED with 4 terminals. Use 3 2-terminal LEDs of colors of your choice instead:
   ```
         |     |     |                    |     |     |                    
         |     |     |                    |     |     |                    
         |     |     |                    |     |     |                    
         |     |     |                    |     |     |                    
         R     G     B         vs         R     G     B                    
         |     |     |                    |     |     |                    
         -------------                    |     |     |
               |                          |     |     |
               |                          |     |     |
   ```

#### 2. Apply
[[toc](#table-of-contents)]  

1. `[<lernact-prac>]`Run the program from the guide, using any 3 LEDs of different color.  
2. `[<lernact-prac>]`Run the same program with 5 LEDs. Feel free to change the pattern.      
3. `[<lernact-prac>]`**[Optional challenge, max 5 extra step points]** Write a program to drive 3 external LEDs driven by 3 `[<cept>]`_sinusoids_ offset at <img src="https://render.githubusercontent.com/render/math?math=2\pi/3"> radians apart.    

#### 3. Present
[[toc](#table-of-contents)]  

In the [programs](programs) directory:

1. Add your program from 10.2.1 with filename `microbit-program-10-2-1.js`.  
2. Add your program from 10.2.2 with filename `microbit-program-10-2-2.js`.  
3. Add your program from 10.2.3 with filename `microbit-program-10-2-3.js`.  

In the [Lab Notebook](README.md):

1. Link to the program from 10.2.1.  
2. Link to a demo video of the operation of the program from 10.2.1.  
1. Link to the program from 10.2.2.  
2. Link to a demo video of the operation of the program from 10.2.2.  
1. Link to the program from 10.2.3.  
2. Link to a demo video of the operation of the program from 10.2.3.  


### Step 11: micro:bit GPIO pins
[[toc](#table-of-contents)]  

#### 1. Study
[[toc](#table-of-contents)]  

##### micro:bit I/O
[[toc](#table-of-contents)]  

The micro:bit performs `[<cept>]`_input_ and `[<cept>]`_output_ through the GPIO pins. It can write or read from each pin individually. It can also perform I/O using `[<cept>]`_serial protocols_ like `[<cept>]`_SPI_ and `[<cept>]`_I2C_. We won't be covering these protocols in this progression as that requires an `[<cept>]`_oscillocope_ to read and demonstrate.    

##### Digital vs analog  
[[toc](#table-of-contents)]  

The GPIO pins can work in two `[<cept>]`_mutually exclusive_ modes:
1. Digital. `[<cept>]`_Ditigal signals_ have one of two values, 0 V, indicating `[<cept>]`_logical 0_, and the maximum circuit operating voltage (which in the case of the micro:bit is 3.3V), indicating `[<cept>]`_logical 1_.  
2. Analog. `[<cept>]`_Analog signals_ have `[<cept>]`_continous_ values in the operating range (in our case is [0V, 3.3V]. An analog signal can have values 0.15V, 1.26V, 3.07V, etc. All signals in Nature are continuous and, therefore, analog. To work with data from analog input, computers convert it to `[<cept>]`_discrete_ (meaning map intervals of the continous signal to discrete values) first. Digital is discrete with only two values. The microbit analog levels from 0 to 1023 are a `[<cept>]`_discretization_ of the range [0V, 3.3V] with 1024 levels. This process is called `[<cept>]`[_analog-to-digital conversion_](https://en.wikipedia.org/wiki/Analog-to-digital_converter). This process, along with its converse `[<cept>]`_digital-to-analog conversion_ go together and are part of every computer system that has to work with analog signals.    

More details on the operation of GPIO pins can be found in the [edge connector documentation](https://tech.microbit.org/hardware/edgeconnector/#pins-and-signals) and the [pin:out](https://microbit.pinout.xyz/) project webpage.   

#### 2. Apply
[[toc](#table-of-contents)]  

1. `[<lernact-prac>]`Write a program to output an analog signal at levels from 0 to 1023, at intervals of 100, for 3 seconds each. Measure the voltage at each level.  
2. `[<lernact-prac>]`Attach our usual LED circuit to an analog pin outputting an analog signal at levels from 0 to 1023, at intervals of 100, for 10 or more seconds each. Measure the voltage drop across the 330 Ohm resistor and the LED at each level.  
3. `[<lernact-prac>]`Connect the multimeter to measure the current through the circuit 11.2.2. Run the same program. Measure the current at each level.  
4. `[<lernact-prac>]`Attach our usual LED circuit to a digital pin outputting an alternating 0 and 1 signal, at intervals of 100, for 10 or more seconds each. Measure the voltage drop across the 330 Ohm resistor and the LED at each level.  
5. `[<lernact-prac>]`Connect the multimeter to measure the current through the circuit 11.2.4. Run the same program. Measure the current at each level.  
6. `[<lernact-prac>]`**[Optional challenge, max 10 extra step points]** Build a circuit with two 330 Ohm resistors in series, driven by an analog pin. Use the program from 11.2.1 to run the pin. Connect the point between the two resistors to another pin, in the analog read mode. Extend the program to:
   1. Read the value of the point between the resistors.   
   2. Use the function `pins.map()` to map the analog range [0, 1023] to the range [0, 9].  
   3. Use columns 0 and 1 to build an output voltage gauge, as follows:
      1. For mapped level [0, 1], light the LED at (0, 4) (bottom left).  
      2. For mapped level [1, 2], light the LEDs at (0, 3) and (0, 4).  
      3. For the next 3 levels, continue lighting 3, 4, or all 5 of column 0.  
      4. For the higher levels, start lighting the LEDs of column 1, from bottom toward top, in addition to the LEDs of column 0.  
   4. Use columns 3 and 4 to build an input voltage gauge.  
   5. Use the input guage to display the mapped analog ouput voltage driving the external circuit.  
   6. Use the output gauge to display the mapped analog input voltgate from the point between the two resistors.  

#### 3. Present
[[toc](#table-of-contents)]  

In the [programs](programs) directory:

1. Add your program from 11.2.1 with filename `microbit-program-11-2-1.js`.  
2. Add your program from 11.2.2 with filename `microbit-program-11-2-2.js`.  
3. Add your program from 11.2.4 with filename `microbit-program-11-2-4.js`.  
4. Add your program from 11.2.6 with filename `microbit-program-11-2-6.js`.  

In the [Lab Notebook](README.md):

1. Link to the program from 11.2.1.  
2. Link to a demo video of the operation of the program from 11.2.1.  
3. Present your measurements from 11.2.1.  
4. Link to the program from 11.2.2.  
5. Link to a demo video of the operation of the program from 11.2.2.  
6. Present your measurements from 11.2.2.  
7. Present your measurements from 11.2.3.  
8. Link to the program from 11.2.4.  
9. Link to a demo video of the operation of the program from 11.2.4.  
10. Present your measurements from 11.2.4.  
11. Present your measurements from 11.2.5.  
12. Link to the program from 11.2.6.  
13. Link to a demo video of the operation of the program from 11.2.6.  


### Step 12: Screensaver extension   
[[toc](#table-of-contents)]  

#### 1. Study
[[toc](#table-of-contents)]  

##### Extending a program
[[toc](#table-of-contents)]  

`[<lernact-rd>]`Extending a program is one of the most frequent tasks in software engineering. It is the complementary converse of iterative development. If you are building a large software or full-stack system, you want to implement it in steps of reasonable size, not too large and not too small. Inevitably, you will be extending an already written program.

Take a look at the following videos to see the goal for this step - extending the 5x5 LED matrix of the micro:bit to a 5x7 matrix with two external LED rows driven by micro:bit GPIO pins:
1. The [coding](https://msudenver.yuja.com/Dashboard/Permalink?authCode=1801242296&b=2060518&linkType=video) screensaver in 5x7.    
2. The [rain](https://msudenver.yuja.com/Dashboard/Permalink?authCode=710066217&b=2060531&linkType=video) screensaver in 5x7.    
3. The [frequency bars](https://msudenver.yuja.com/Dashboard/Permalink?authCode=1488262525&b=2060499&linkType=video) screensaver in 5x7.    

The first five rows are commanded with functions from the `led` namespace, while the last 2 are commanded with functions from the `pins` namespace. While analog output pins may work for the whole screensavers program, especially when we want to have different brightness (aka intensity), the coding program can use digital output pins. In this sense, the following table shows the equivalent statements:

Analog pin | Digital pin
--- | ---
`pins.analogWritePin(AnalogPin.P0, 0)` | `pins.digitalWritePin(DigitalPin.P0, 0)`
`pins.analogWritePin(AnalogPin.P0, 1023)` | `pins.digitalWritePin(DigitalPin.P0, 1)`

##### Defining extra rows
[[toc](#table-of-contents)]  

The best way to declare the extra rows is the one that will let you insert and/or modify minimal sections of the programs you are extending. Consider a 2D array, where you have two rows of 5 pins. See the following example:
```javascript
// Example 12.1.1

let led_rows : AnalogPin[] = [
    [[AnalogPin.P0], [AnalogPin.P2]],
    [[AnalogPin.P1], [AnalogPin.P8]]
]
```
Notice the following:
1. The enumerated types `AnalogPin` and `DigitalPin` are mutually exclusive. That is, you can't use the same pin as both digital and analog in the same program.  
2. You can organize the pins for the external LEDs in two different way, which equivalent except when it comes to index ordering in the 2D array selectors:
   1. By rows:
      ```javascript
      // Example 12.1.2

      let led_rows : AnalogPin[] = [
          [[AnalogPin.P0], [AnalogPin.P2], [], [], []],
          [[AnalogPin.P1], [AnalogPin.P8], [], [], []]
      ]
      ```
      in which case the selectors are ordered as `[y][x]`, and
   2. By columns:
      ```javascript
      // Example 12.1.3

      let led_cols : AnalogPin[] = [
          [[AnalogPin.P0], [AnalogPin.P1]],
          [[AnalogPin.P2], [AnalogPin.P8]],
          [[], []],
          [[], []],
          [[], []]
      ]
      ```
      in which case the selectors are ordered as `[x][y]`.

##### Choice of pins
[[toc](#table-of-contents)]  

There are a handful of factors that may affect the choice of pins for the two extra (external) LED rows:
1. We need 10 pins that are not used for anything else. This means that we are going to run them with the single-pin write and read functions of the `pins` namespace.  
2. We need the 5x5 LED matrix anaffected so that the original screensaver sub-programs display correctly. This means we cannot use the pins that are involved in running the LED matrix.  
3. We have limited breadboard real estate below the micro:bit edge connector. This means we we want to pick maximally adjacent pins to drive adjacent LEDs.  
4. The two pins used for the serial protocol I2C, namely `P19` and `P20`, would require extra `[<cept>]`_pull-down_ resistors to work, so they are not a good choice.  
5. Putting together the count of available pins, we might need to sequester one or both of the pins connected to the buttons. _Note that, if you are doing the optional challenge at the end, you will need to leave one button pin unused and make that button a mode toggle._  

#### 2. Apply
[[toc](#table-of-contents)]  

1. `[<lernact-prac>]`Build the two external rows of LEDs and program a row to continuously move up and down the 7 vertical positions (5 from the micro:bit LED matrix and 2 on external LEDs driven by micro:bit pins).  
2. `[<lernact-prac>]`Extend the code-writing program to work with the 7 rows of LEDs.  
3. `[<lernact-prac>]`Extend the rain screensaver to work with the 7 rows of LEDs.  
4. `[<lernact-prac>]`Extend the frequency bar screensaver to work with the 7 rows of LEDs.  
5. `[<lernact-prac>]`**[Optional challenge, max 10 extra step points]** Extend the whole screesavers application to work with the 5x7 format and tag it `v2.0`.  

#### 3. Present
[[toc](#table-of-contents)]

In the [programs](programs) directory:

1. Add your program from 12.2.1 with filename `microbit-program-12-2-1.js`.  
2. Add your program from 12.2.2 with filename `microbit-program-12-2-2.js`.  
3. Add your program from 12.2.3 with filename `microbit-program-12-2-3.js`.  
4. Add your program from 12.2.4 with filename `microbit-program-12-2-4.js`.  
5. Add your program from 12.2.5 with filename `microbit-program-12-2-5.js`.  

In the [Lab Notebook](README.md):

1. Link to the program from 12.2.1.  
2. Link to a demo video of the operation of the program from 12.2.1.  
2. Link to the program from 12.2.2.  
2. Link to a demo video of the operation of the program from 12.2.2.  
3. Link to the program from 12.2.3.  
2. Link to a demo video of the operation of the program from 12.2.3.  
4. Link to the program from 12.2.4.  
2. Link to a demo video of the operation of the program from 12.2.4.  
5. Link to the program from 12.2.5.  
2. Link to a demo video of the operation of the program from 12.2.5.  
6. Link to the tag for the program from 12.2.5.  
