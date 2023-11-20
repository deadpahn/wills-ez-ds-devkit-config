!["ez ds bootstrap](logo.png)

Trying to make it super easy to get your environment set up for Nintendo DS development

After hours and hours of trying to figure out what the hell is going on, I finally figured out how to compile this.

# tl;dr
- git clone this project
- make a folder in the newly cloned directory (this is where you will put your DS code)
- follow the steps in the "Docker config" section below

# Elevator pitch
Creating DS software requires figuring it out on your own. However, this repository aims to eliminate the frustrating process of deciphering all the necessary components that must work seamlessly before your code evolves into a Nintendo DS application. Imagine wanting to develop a game in Unity or Unreal Engine, but instead of effortlessly downloading the program from their website, you find yourself sifting through countless blog posts, forums, Reddit threads, encountering compile errors due to unfamiliar technologies, and more. As developers, we don't want these hurdles. Some may find them acceptable, but our goal is to let you focus on making your software function, not on grappling with toolchains. I am committed to providing a comprehensive package that minimizes the steps needed to kickstart your journey and design your dream game or app. The Nintendo DS is an incredible platform, akin to something out of a dream; coding for it should be a delight, not a nightmare.


# What is docker?
In short, Docker serves a purpose similar to the DS, using figurative language. Instead of manually downloading various components and piecing them together, Docker allows one to create a configuration or "container." This container enables developers to seamlessly begin working on their projects without getting bogged down by the trivial complexities of ensuring compatibility between X and Y or keeping Z up-to-date with X. Imagine it as inserting a game cartridge into the DS and simply pressing power to see the game appear on the screen. In contrast, it eliminates the need for players to install toolchains on their computers and compile their own code.

Thankfully devkitpro supports docker now (https://github.com/devkitPro/docker) but there is still a lot of glue that a newbie might struggle with. It also helps having a list of learning resources (see the "Learning Resources" section of this document).

## Docker config
Very work in progress instructions but here goes:

git clone this branch and enter it via the sCaRy TeRmInAl.

run:

Download devkitpro docker image and configure things:

`docker-compose build`

after everything downloads and stuff run

`docker-compose up`

### Enter the container:

`docker-compose exec devkitpro /bin/bash`

### once in the container run:

`apt install pip`

`pip install pillow`

`pip install image`
(I know I should have this in the Dockerfile but it wasn't working I'll fix it later)
 
### How the hell do I make the .nds file now? 

In the root folder you can run: 

`docker-compose exec devkitpro make`

## OR 

you can use:

`docker-compose exec devkitpro /bin/bash`

and navigate the file system and use make from there.

# Learning Resources

### Examples

Look at the tutorials folder for examples. See if you can `make` some of the example projects.

### Read other peoples code!

Thankfully there are more projects on Github now relating to this.

### Videos

- great video of Break bad home brew game: https://www.youtube.com/watch?v=HiiZxOU934E
- MVG made a nice overview of the graphics on the NDS: https://www.youtube.com/watch?v=kBgQJJ93nFM

### Guides and References

- Big N's official docs maybe? https://archive.org/details/NitroDevDocs
- This is an ebook but you can read the free version on their site https://www.copetti.org/writings/consoles/nintendo-ds/
- Great repo with more code examples and teachings https://github.com/jdriselvato/NDS-Homebrew-Development
- Another nice over view of NDS development stuff https://www.chibialiens.com/arm/nds.php
- NDS Homebew Development https://github.com/jdriselvato/NDS-Homebrew-Development
- GBA dev stuff but probably still helpful https://www.coranac.com/tonc/text/toc.htm

### Code to study

- https://github.com/vrodin/Burn2Slot
- https://github.com/AntonioND/nitro-engine
- https://github.com/Fewnity/Nintendo-DS-Nifi-Template
- https://github.com/WiIIiam278/breaking-bad-ds
- https://github.com/asiekierka/nitrotracker
- https://github.com/rhaleblian/dslibris
- https://github.com/FluBBaOfWard/NGPDS
- https://github.com/FluBBaOfWard/NitroSwan



# Final thoughts

Happy Hacking!
