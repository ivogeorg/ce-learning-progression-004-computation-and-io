# CPE 1040 - Spring 2020

## Assignment 3.5: Microbit Wired & Wireless Roundtrip Communication

Author: Ivo Georgiev, PhD  
Last updated: 2020-02-14  
Code: 333fe0348d8c8a00b82d3e4d9eab4a63a7a5dace  

This is an _optional_ assignment for the Spring 2020 installment of the CPE 1040 - Intro to Computer Engineering course at MSU Denver.

### Overview

This assignment explores wireless and wired I/O communication features of the micro:bit.

### Requirements

#### 1. Radio communcation

1. Use the micro:bit [radio functions](https://makecode.microbit.org/reference/radio) to communicate different data types between 2 micro:bits:
   1. An integer.
   2. A floating-point number.
   3. A boolean.
   4. A single character.
   5. A string.
   6. **(Challenge)** An object of a class. _Hint: Objects are implemented as [key-value maps](https://www.microsoft.com/en-us/research/uploads/prod/2019/09/static-typescript-draft2.pdf) in TypeScript._

2. **(Challenge)** How would you transfer a function across the radio transmission channel that the micro:bit affords?

3. Briefly explain your code in the [experiments](#experiments) section of this [README](README).

4. Record a video that shows the communication, upload to Imgur, and link in the [demo video](#demo-video) section of this [README](README).

#### 2. GPIO pin communication

1. **(Challenge)** Use the micro:bit [GPIO pin functions](https://makecode.microbit.org/reference/pins) to communicate different data types between 2 micro:bits (_Hint: You might want to consider creating your own protocol and an API like the `sendValue()` and `onReceivedValue()`.):
   1. An integer.
   2. A floating-point number.
   3. A boolean.
   4. A single character.
   5. A string.
   6. An object of a class.

2. Briefly explain your code in the [experiments](#experiments) section of this [README](README).

3. Record a video that shows the communication, upload to Imgur, and link in the [demo video](#demo-video) section of this [README](README).

#### 3. Round-trip communication

1. Measure the time it takes for the round-trip communication, using only _radio_, of a:
   1. Number.
   2. String. _How do you signal the end of the string? How does the length of the string affect the time?_
   
2. Repeat the experiment from (1), now using only _pins_.

3. Repeat the experiment from (1), now using _radio_ in one direction, and _pins_ in the reverse direction.

4. Briefly explain your code in the [experiments](#experiments) section of this [README](README).

5. Record a video that shows the communication, upload to Imgur, and link in the [demo video](#demo-video) section of this [README](README).

#### 4. (Challenge) Clock synchronization

1. Create a MM:SS _binary-coded decimal_ clock to display on the LED matrix of the micro:bit. Can you make it run at the correct speed?

2. Once you are done with (1), create a clock-sync procedure between the 2 micro:bits. Note that the second micro:bit should only receive time and time corrections from the first one. Can you get the two micro:bits to run in sync?

3. Explain your code in the [experiments](#experiments) section of this [README](README).

4. Record a video that shows the communication, upload to Imgur, and link in the [demo video](#demo-video) section of this [README](README).

## Resources

### micro:bit 

1. [micro:bit lessons](https://makecode.microbit.org/lessons).

2. [micro:bit ideas](https://microbit.org/ideas/).

3. A list of some more [advanced projects](https://www.itpro.co.uk/desktop-hardware/26289/13-top-bbc-micro-bit-projects).

4. The [projects](https://github.com/carlosperate/awesome-microbit#%EF%B8%8F-projects) at the [awesome micro:bit list](https://github.com/carlosperate/awesome-microbit).

5. micro:bit [technical documentation](https://tech.microbit.org/).

### Github

1. Github Tutorial for Beginners ([webpage](https://product.hubspot.com/blog/git-and-github-tutorial-for-beginners)).

2. Github Basics for Mac and Windows ([video](https://www.youtube.com/watch?v=0fKg7e37bQE)).

3. git & Github Crash Course for Beginners ([video](https://www.youtube.com/watch?v=SWYqp7iY_Tc)).

4. Introduction to Github for Beginners ([video](https://www.youtube.com/watch?v=fQLK8Ib_SKk)).

5. About `git` ([webpage](https://git-scm.com/about)).

6. `git` [documentation](https://git-scm.com/doc) (webpage, book, videos, reference manual).

7. [Github markdown cheat sheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet).

### JavaScript

1. Technically, the language which is used side-by-side with Blocks in the Makecode ronment is a subset of [TypeScript](https://makecode.com/language), which itself is a superset of JavaScript (technically, [ECMAScript](https://www.ecma-international.org/ecma-262/10.0/index.html#Title)), with some JS features not implemented in Makecode.

2. The limited [JavaScript mini-tutorial](https://makecode.microbit.org/javascript) in Makecode.

3. Official [TypeScript documentation](https://www.typescriptlang.org/docs/home.html):
   1. TypeScript in 5 min [tutorial](https://www.typescriptlang.org/docs/handbook/typescript-in-5-minutes.html). _Note: You will need to [download](https://www.typescriptlang.org/index.html#download-links) and install an integrated development environment (IDE). The two that I recommend are Visual Studio Code from Microsoft and WebStorm from JetBrains._
   2. The full documentation and reference is under _Handbook_. Bear in mind that you are drinking from the hose. Don't be surprised if not everything is presented in a strictly incremental manner.
   
4. In-browser TypeScript [playground](https://www.typescriptlang.org/play/index.html). Note that micro:bit specific code will not run, but you can still play. _Start making the distinction between a generic multi-purpose programming language (TypeScript) and functionality (packages, libraries, objects, etc.) that is specific to a particular device (micro:bit), though written in the same programming language._

5. A pretty good and very palatable JS tutorial with in-browser coding, by [Codecademy](https://www.codecademy.com/learn/introduction-to-javascript).

6. Extensive and detailed [JS tutorial](https://javascript.info/), with some advanced material thrown in. **I like this one!**

7. The most authoritative JS resource on the Web, including tutorials and reference, by [Mozilla](https://developer.mozilla.org/en-US/docs/Web/JavaScript).

---

## Experiements

_TODO: Describe your communications code, experiements, and comms time-measurements here._

## Demo video

_TODO: Add your video descriptions and URLs here. The videos should clearly show the transmitted values at the origin and destination._
