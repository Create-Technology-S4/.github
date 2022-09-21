<br />

<p align="center"> 
  <a href="https://rently-io.herokuapp.com/">
    <img src="https://i.imgur.com/cGIueqo.png" alt="Title" width="auto" height="60">
  <a/>
</p>

<h4 align="center">Noah Greff - 433819</h4>
<p align="center">This organisation serves as my portfolio for my 4th semester at Fontys University of Applied Sciences in Creative Technology.</p>
<p align="center">This document will evolve overtime.</p>

<br/>

<details>
  <summary>Table of content</summary>
  
  <h3>About Me</h3>
  <ul><li><a href="#day-7679_">Day #7679_</a></li></ul>

  <h3>Projects</h3>
  <ul><li><a href="#individual-project">Individual Project</a></li></ul>
  <ul><li><a href="#duo-project">Duo Project</a></li></ul>
  <ul><li><a href="#client-project">Client Project</a></li></ul>

  <h3>Learning Outcomes</h3>
  <ul><li><a href="#vision">Vision</a></li></ul>
  <ul><li><a href="#innovative-concept">Innovative concept</a></li></ul>
  <ul><li><a href="#interactive-user-experience">Interactive user experience</a></li></ul>
  <ul><li><a href="#prototypes">Prototypes</a></li></ul>
  <ul><li><a href="#present">Present</a></li></ul>
  <ul><li><a href="#personal-growth">Personal growth</a></li></ul>
</details>

# About Me

<br />

> ### Day #7679_

_I go by the "Noah" here. It's been just over 21 years that I have spawned into this world._

_I have been able to travel their world. I have lived in places they name "USA", "France" and "China", the latter of which I have spent over half of my time. Does that make me "chinese"?_

_I have become accustomed to their ways of thinking and doing things. In particular, their ways of working with technology._

_I am pursuing some academic studies in the field of software engineering; currently in my 4th semester. For this semester, they seem to put emphasis on the creativity aspect of using technology to achieve something._

_For the remainder of my time in this world, I truly hope to have some lasting, positive impact no matter how small._

<br/>

# Projects

## Individual Project

> Name:     **Intuitive Computer Interaction**

> Duration: **2 Weeks**

This project, although relatively small, was our first project. It acted as an introductory project where we had complete freedom to choose whatever we want to work on, so long as it was creative technology-related. 

# 

The source code of my project can be found here:

<a href="https://github.com/Creative-Technology-S4/Individual-Project" >
  <img src="https://github-readme-stats.vercel.app/api/pin/?username=Creative-Technology-S4&repo=Individual-Project&include_all_commits=true&show_owner=true" /> 
</a>

#

### Conceptualization

When I was first introduced to what it means to be a creative technologist, one thing struck me in particular: user interactivity. Essentially, how will viewers/users interact with your work. With this in mind, I started brainstorming some ideas of what I could potentially do for my project.

As a software student, my area of expertise in technology is definitively software. However, when I think about user interactivity, there is always some hardware element that is used to control something virtually. Luckily, we were given various arduino components to play around with. I had all the ingredients I needed to make something interactive.

There is a lot of different places I could combine software and hardware to make something interact. To me, the domain that makes the most sense for such an idea is a video game. Due to the time constraints, I did not want to make build a game from scratch as that was not the main focus of my project, so I settled on using a game that already existed and choose the game _Minecraft_.

3D video games typically use some peripherals that allows the player to control a character. Specifically, the mouse is used to control the direction of the character's viewport (camera) and the keyboard trigger motion and I thought why not replace one of the peripherals with one of the components given. For my idea, I decided to use the gyroscope to control the camera. Why not map the gyroscope's orientation vector to the directional vector of the camera?

### Prototyping

To make my idea come to light, I had to break down my project into smaller steps since I have never worked on such an idea before. Throughout this project, I came up with 3 different prototype where, to my surprise, we can clearly depict an evolution.

#### First Attempt

My first attempt was very much an experimental phase where I was familiarizing myself with programming for arduino's. 

Beyond that, this first attempt was all about trying establishing a communication line between the arduino and the game. I initially wanted to achieve this wirelessly but the complexity of such a thing would be time-consuming and that was beyond the scope of what my project so ended using the arduino's serial port to send data.

As a proof of concept, I decided to use a potentiometer to simply change the time of day in the game's world as shown in the first image below (left).

This initial prototype, albeit very basic, took me the longest to achieve as it was all about being able to send data from an analog input into the game. The second image (right) shows the first result of my work. As can be seen, the delay between the input and the ingame time being updated is _very_ large. There is Approximately 9 seconds between an input and an update which is nowhere near as fast as it needs to be for a good user interaction. So I set out to make my second prototype.

<p align="center">
  <img src="docs/individual-project/setup.jpg" height="500" />
  <img src="docs/individual-project/first.gif" height="500" />
</p>

#### Second Attempt

My second prototype was all about increasing the response time between an input and an update. Although the hardware setup remained identical, most of the changes were software-related. I figured if the arduino by itself is capable printing its value extremely fast on the serial monitor on my computer than the delay is most likely software-related. 

After some _long_ nights (which eventually turned into short mornings) I have completely changed the way data is received by the game and was ultimately able to achieve a response time that had no noticeable delays. In addition, now instead of sending primitive types as strings, I can send data in JSON format (with [this class](https://github.com/Creative-Technology-S4/Individual-Project/blob/master/src/main/java/me/noahgreff/s4ct/SerialPortJsonReader.java) in a [neat way](https://github.com/Creative-Technology-S4/Individual-Project/blob/master/src/main/java/me/noahgreff/s4ct/Main.java#L30)) which greatly increases the flexibility I have for adding more components in the future (such as the gyroscope). 

Ultimately, the only delay was that of the game's update frequency which is 20hz. For user interactivity, this was fine. The results are shown below.

<p align="center">
  <img src="docs/individual-project/second.gif" height="500" />
</p>

#### Final Attempt

For my third and final attempt, I set out to actually implement the gyroscope to control the character's camera. This final prototype was relatively quick to implement as most the useful and time-consuming work has been done by the prior prototypes. It was just a matter of listening for the right data and updating the camera's angle on every tick (20 times per second). 

This resulted in the demo below.

<p align="center">
  <img src="docs/individual-project/third.gif" height="500" />
</p>

## Reflection

This project has been really fun to work on. Unlike most project I worked on in the past, the short time given has given me a new way of working in the sense that I had to focus on the stuff that mattered most. This project felt like it was more of a hackathon to quickly get ideas into form. I wished I was given more time to work on this as I think I would have been able to polish my example way more and perhaps even integrate a component to also trigger movement.

I am happy with the outcome of the project. I can now interact with the game using a gyroscope and I think it is really cool.

<br/>

## Duo Project

> 🚧 [Under Construction] 🚧

<br/>

## Client Project

> 🚧 [Under Construction] 🚧

<br/>

# Learning Outcomes

### Vision

> You express your own vision on future scenarios through research of the evolution of mankind’s relationship with technology.

#### Week 4

When thinking about the relationship between humans and technology, the only practical way someone can interact with a computer is via the typical mouse and keyboard. I was thinking whether this would always be the case. What if we removed the mouse or keyboard? What would be another peripheral that can be used instead, a camera? I wanted to explore this a bit more in my personal project and built an analog controller that (partially) removes the need to use a mouse to play in the game Minecraft.

#

### Innovative concept

> You discover and define an innovative concept using creative thinking techniques combined with research of technology, context and human.

#### Week 4

For my personal project, I have spent some time investigating possible ways in which someone can interact with computers without a mouse and keyboard. Initially, I wanted to use a camera and detect the direction of the user and map this to the character's camera however, if the user wanted to look up in the game they would have to look up themselves which would make looking on the screen difficult. A better way was to use a gyroscope that could be held and used as a joystick.  

#

### Interactive user experience

> You design an experimental interactive user experience that investigates a technology’s potential and its mutual effect on people.

#### Week 4

Perhaps the most intriguing work I have done so far almost entirely revolved around user interaction. In my personal project, I have explored ways someone can play a video game through hand motion. I was thinking about what would be the most fun and, more importantly, more intuitive way someone can control a character's camera. Of the components that were given, I saw the gyroscope as having the most potential to emulate natural user interaction.

#

### Prototypes

> You collaboratively realize and test a series of prototypes and its potential, for both users and stakeholders, in real-world application.

#### Week 4

In my personal project, I did a series of prototypes which were incrementally better compared to the previous version. Through prototyping, I was able to break down challenging problems into smaller, more manageable problems. This has ultimately allowed me to quickly add additional functionalities as I had a clearer vision of the final product. Had this project continued, I believe that I would have been able to add more controls rapidly.

#

### Present

> You present your research outcomes, prototypes and reflections in relation to your research, concept and vision, to stakeholders, peers and potential future employers.


#### Week 4

During the demo day, I prepared a presentation showcasing my idea, process and impact of my product. However, I believed that the result of my project was more than just something to present via a presentation and I prepared the game along with the gyroscope for people to use experience the controls for themselves. This made my demonstration more interactive and engaging to people.

#

### Personal growth

> You articulate your professional ambitions and focus and demonstrate your efforts and growth within the roles you fulfill in your projects.

#### Week 4

Being a student from the software branch, my comfort zone is software programming however, I always wanted to use my skills to build something fun and interactive such as controlling a drone with a VR headset but never knew how to link software and hardware together. The personal project has given me the opportunity to focus exactly on that. In the future, I would like to work more on projects like this.
