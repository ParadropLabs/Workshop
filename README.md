# Paradrop Workshop

## Prerequisites

In order to get the most out of the workshop, you should familiarize yourself with these materials before the workshop.

### Git

During the workshop, you will use git to collabortively develop chutes and deploy them to a Paradrop device.

1. Sign up for a github account if you do not have one.
2. If you have never used git before, some of the commands can be unintuitive or behave very differently from other version control systems.  Try out this 15-minute [tutorial](https://try.github.io).

### Node.js + Express

We will build a simple Node.js application using Express during the workshop, and it will help if you have seen Express.js before.

1. Try out their [Hello World](https://expressjs.com/en/starter/hello-world.html), and you will be good to go.

### Docker

Paradrop uses Docker to run chutes in what are called "containers".
These containers include all of the chutes's dependencies and provide
some isolation from other apps running on the same device but have
lower overhead than virtual machines.  We will not be working with
Docker directly during this workshop, but some knowledge of how Docker
works will help you later on when you are debugging or developing more
advanced applications.

1. Start with [What is Docker?](https://www.docker.com/what-docker) for an overview.
2. Look through the [Getting Started](https://docs.docker.com/engine/getstarted/) guide.  The most important section for developing with Paradrop is the one on [writing a Dockerfile](https://docs.docker.com/engine/getstarted/step_four/).
3. Become familiar with the Docker [command line utility](https://docs.docker.com/engine/tutorials/dockerizing/).  You will not be able to try these commands on your own computer unless you install Docker first.  However, you will have the chance to interact with Docker on the Paradrop routers, so it will help to be familiar with it.
4. (Optional) For the very motivated, there are three one-hour [instructional videos](https://training.docker.com/self-paced-training).

## Example Chutes

Your group will work on several Paradrop chutes during the workshop.  We have posted starter projects on github that you can fork and start working.

### Security Camera

This chute implements a motion detection system using a wireless camera.

[Security Camera Chute](https://github.com/ParadropLabs/Security-Cam)

### Sticky Board

This chute lets people post photos to a local image board that
is visible to whoever is connected to your Wi-Fi access point.
We will build this chute from scratch by following the tutorial.

[Tutorial](http://paradrop.readthedocs.io/en/latest/chutes/tutorial-sticky-board.html).

[Sticky Board Chute](https://github.com/ParadropLabs/StickyBoard).

### Cells

This chute is a multiplayer action game similar to agar.io.

[Cells](https://github.com/ParadropLabs/Cells).

## Other Example Chutes

The following chutes have been used in previous workshops and serve as
examples of other applications that can be built to run on Paradrop.

### Network Test

This chute runs periodic network tests and displays the results in a webpage.

[Network Test Starter Chute](https://github.com/ParadropLabs/NetworkTestStarterChute)

### Parental Control

This chute runs a WiFi access point with content filtering and configurable blocking.

[Parental Control Starter Chute](https://github.com/ParadropLabs/ParentalControlStarterChute)

### Tor

This chute, developed by a previous workshop attendee, sets up a Wi-Fi
AP that directs all traffic through Tor.

[Tor Chute](https://github.com/morehouse/paradrop-tor)

## Debugging a Chute

The Paradrop routers have SSH access enabled.  You can use this to
inspect the running state and filesystem contents of your chutes.
You will be given login details during the workshop.

### List running Docker containers

```bash
sudo docker ps --all
```

If you have a chute installed and running, you should notice a line with
the chute name.

### Open a shell inside a chute's container

```bash
sudo docker exec -it <chute name> /bin/bash
```

With this shell, you can read and modify files inside the chute.  If you
wish to make your code changes permanent, remember to add them to your
git repository.
