<h1>Checkpoint Talk: Operating Systems and Development Environments</h1>

![](./img/small_headshot.png)

<h2>With Oliver Lavers</h2>

Hi folks, I'm Oliver! Welcome to my She Codes Checkpoint Talk. This Github repo contains all the high-points from my talk, as well as any diagrams or code demos I used over the course of the evening.

In this talk I'll be discussing the following topics:

- [What Is A Development Environment?](#what-is-a-development-environment)
- [Operating Systems - What Do Developers Need To Know?](#operating-systems---what-do-developers-need-to-know)
  - [How Computers Work](#how-computers-work)
    - [The Hard Drive](#the-hard-drive)
    - [RAM](#ram)
    - [The CPU](#the-cpu)
  - [The Operating System](#the-operating-system)
    - [The Kernel](#the-kernel)
    - [The Shell](#the-shell)
      - [The Terminal](#the-terminal)
- [Development Environment Management - Why Bother?](#development-environment-management---why-bother)
  - [Reproducibility](#reproducibility)
  - [Dependency Management](#dependency-management)
  - [A Smoother Path](#a-smoother-path)
- [Important Factors in Dev. Environment Choice](#important-factors-in-dev-environment-choice)
  - [The Big Three](#the-big-three)
  - [End Goals](#end-goals)
  - [Ease Of Setup](#ease-of-setup)
- [What You Need To Get Started](#what-you-need-to-get-started)
  - [OS](#os)
  - [Terminal](#terminal)
  - [Shell](#shell)
  - [Editor](#editor)
  - [Version Control](#version-control)
  - [Dependency Management](#dependency-management-1)
    - [For Python](#for-python)
    - [For Javasript](#for-javasript)
    - [For Others](#for-others)
  - [What's This About Debuggers?](#whats-this-about-debuggers)
  - [Peripheral Tools](#peripheral-tools)
    - [Text Editing](#text-editing)
    - [Diagramming](#diagramming)
    - [Document Creation](#document-creation)
    - [Project Management](#project-management)
    - [Data Analysis/Dashboarding](#data-analysisdashboarding)
    - [Communication](#communication)
- [Paths To Becoming A Dev. Environment Blackbelt](#paths-to-becoming-a-dev-environment-blackbelt)
  - [Dev Environment Upgrades](#dev-environment-upgrades)
  - [Becoming Multilingual](#becoming-multilingual)
  - [Computer Science Theory](#computer-science-theory)

This might seem like a lot of info to get through about if you're just getting into coding, but trust me - this is what I wish I had known before I ever set finger to keyboard. 

It might also seem like these are two pretty separate topics. In fact, they are tightly bound to one another. When you are making decisions about how to set up your development environment, an understanding of the operating system can be crucial.

A little bit of background here can give you the context you need to launch yourself into the most intimidating parts of coding with gusto. The path to being a blackbelt hacker doesn't have an end, but this is a good way to begin!

![](./img/neo.gif)
> Actual footage of you on your journey to programming glory.

## What Is A Development Environment?

## Operating Systems - What Do Developers Need To Know?
### How Computers Work
> Yep, we are getting down to the really tricky bits right away.

There's an extent to which the theory of computer science actually gets in the way of understanding how this stuff works. The field has turned into a very abstract branch of engineering, which means that the hidden secrets of IT are quite divorced from the point at which the rubber meets the road.

For instance, we often hear that computers run on binary code - `1`'s and `0`s. This is 100% true, and also **100% useless** when it comes to the practical work that a beginner can engage with.

Here's a better explanation:

![](./img/magic.gif)

Seriously. Just imagine for a moment that there are elves inside each component of the computer, and they do what they're told to on command. It simplifies the discussion, and it really doesn't give you any less information.

Let's take a look at some of those components:

#### The Hard Drive
![](./img/hard_drive.jpg)
This element is used for long term storage of information. It's the computer equivalent of long term memory. Files live here, and are made up of text or binary data.

#### RAM
![](./img/ram.jpg)

> (AKA - **R**andom **A**ccess **M**emory)

This element is used for short-term storage of information. The computer equivalent of short-term or working memory. This is where the variables we use in our code are stored while our programs are running.

#### The CPU
![](./img/cpu.jpg)

> (AKA - **C**entral **P**rocessing **U**nit)

This element is the computer equivalent of a frontal lobe. It is the physical part of the hardware that can manipulate information. 

It doesn't independently know *how* it should manipulate information, though. On its own it would just sit there like a big chunk of inanimate silicon. 

To do anything useful it needs some secret sauce...

### The Operating System
![](./img/os.png)

> (AKA - "**OS**")

This element is software, not hardware. It's a the most fundamental program that your computer knows how to run.

The operating system is stored on the hard drive. Every time the computer is turned on, it immediately gets loaded into the CPU, and starts telling it how to be a computer. 

The operating system tells the CPU how to find your files, what to display on the screen, how to understand the other programs, and how to respond to your requests. 

This means that everything else that happens on your computer has your operating system as its foundation. Any program that runs on your machine needs to be crafted to fit your particular operating system, and the ways that you can interact with the computer will be governed by the operating system's specifications.

The operating system is broken up into two major components, using the metaphor of a seed...

![](./img/seed_diagram.drawio.png)

#### The Kernel
![](./img/ophanim.svg)

> Artist's impression only...

The kernel is the core of the OS. It interacts with all the various components of the computer, speaking in their language. It talks to your monitor the way a monitor is capable of understanding. It speaks keyboard-language to your keyboard. It corrals the memory and the CPU and all the other bits and pieces.

I've represented the kernel up there as an otherworldly being, because it isn't really designed to be comprehensible by human beings. It is designed to be terrifyingly efficient, and to be comprehensible by computer hardware.

Thats why we need...

#### The Shell

![](./img/switchboard.jpeg)

The shell is the outer wrapper of the OS. It acts as a translator between the user and the kernel, making it easy to tell the computer what to do. 

The user hands instructions to the shell. The shell translates them into something the kernel can understand. Then the kernel goes and musters all the resources of the computer to try and deliver what the user asked for.

Most of the time you can actually pick and choose between a variety of shells that are designed to work with your operating system, and picking your shell is one of the important aspects of setting up a development environment.

So, where can we find the shell to talk to it?

##### The Terminal 

![](./img/terminal.png)

The terminal is a text input/output program that lets you talk to your shell. 

Because you very seldom interact with the shell except through the terminal, it's easy to get them confused. In fact, a lot of popular shells come bundled with their own terminal.

Just keep in mind, behind the scenes and under the hood, they're separate, and that means that you can often use the same terminal to interact with a variety of different shells!

## Development Environment Management - Why Bother?
Ok, that was a lot. So how does it motivate us to think about dev. environments?

Well, think about this: there are a bunch of different operating systems out there. That means that every developer's computer has its own quirks and specific circumstances. And *that* means that each developer needs to learn how best to work with the operating system that they are using.

In particular...

### Reproducibility
We need a way to make sure that the code that runs on our development machine will run on other people's machines! After all, what's the point of writing a program that nobody can ever use?

If you're making websites, you need to make sure that your websites can be served from a Linux machine, because that's probably what will be serving them when you deploy them.

If you're writing desktop apps, you need to make sure that your desktop interacts with your programs the same way that your users' machines will.

And if you're coding in a team, you need to make sure that you are producing work that your colleagues can make use of on their own machines. 

### Dependency Management


### A Smoother Path

## Important Factors in Dev. Environment Choice
### The Big Three

### End Goals

### Ease Of Setup

## What You Need To Get Started
### OS

### Terminal

### Shell

### Editor

### Version Control

### Dependency Management 
#### For Python

#### For Javasript

#### For Others

### What's This About Debuggers?

### Peripheral Tools
#### Text Editing

#### Diagramming

#### Document Creation

#### Project Management

#### Data Analysis/Dashboarding

#### Communication

## Paths To Becoming A Dev. Environment Blackbelt
### Dev Environment Upgrades

### Becoming Multilingual

### Computer Science Theory