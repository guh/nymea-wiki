# Install *guh*-core on Debian

--------------------------------------------
| Debian     |  Wheezy 7.0  |  Jessie 8.0  |
|:-----------|-------------:|:------------:|
| `amd64`    |       ✘      |       ✔      |
| `i386`     |       ✘      |       ✔      |
| `armhf`    |       ✘      |       ✔      |
--------------------------------------------

In order to install *guh* on Debian you need to create the `/etc/apt/sources.list.d/guh.list` file and add the *guh*-repository:

1. Create the [*guh*-repository](http://repo.guh.guru/) list file:
        
        $ sudo nano /etc/apt/sources.list.d/guh.list
        
    In the repository are following distributions available:
    * `jessie` 

    Available architectures are `amd64` `i386` and `armhf`.
    
    > *Note:* You can get your system version with `cat /etc/os-release`. 

    Copy following lines into the file and save it:

        ## guh repo
        deb http://repo.guh.guru jessie main
        deb-src http://repo.guh.guru jessie main
        

    > **Alternative:** `$ echo -e "\n## guh repo\ndeb http://repo.guh.guru jessie main\ndeb-src http://repo.guh.guru jessie main" | sudo tee /etc/apt/sources.list.d/guh.list`
    
    Add the public key of the [*guh*-repo](http://repo.guh.guru/) to your keylist.
    
        $ sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-key 6B9376B0
    
        
2. Update your package lists:
    
        $ sudo apt-get update

    The *guh*-repo provides following packages:
    
        $ apt-cache search guh
    
        guh - An open source IoT server - meta package
        guh-cli - guh command line interface - python
        guh-dbg - An open source IoT server - debug symbols
        guh-doc - Documentation for the guh package (on-site) - documentation
        guh-plugins - Plugins for guh IoT server
        guh-tests - Tests for the guh package
        guh-webinterface - Browser based user interface for guh
        guh-webinterface-doc - Documentation of the guh webinterface source code (on-site) - documentation
        guhd - An open source IoT server - daemon
        libguh1 - An open source IoT server - core library
        libguh1-dev - An open source IoT server - development files

3. Install *guh* with following command:
    
        $ sudo apt-get install guh guh-cli guh-webinterface
        
    The repository contains always the latest stable build of the *guh* `master` branch. 
    If you want to install the source code you can install:
        
        $ sudo apt-get source guh        
        $ sudo apt-get source guh-cli
        $ sudo apt-get source guh-webinterface
        
Once, the installation is finished you continue with the [[Getting started]] instruction.