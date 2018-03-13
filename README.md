purdue-ctf
================

`purdue-ctf` is the CTF management system used by the Purdue Cyber Forensics club.

![Image of Purdue CTF](https://i.imgur.com/xxresvd.png "purdue-ctf in action")

Deployment
----------

To deploy `purdue-ctf` on an EC2 instance, execute the following commands:

Become root, upgrade

    sudo su
    yum upgrade -y
    
Install some prerequisites

    yum install -y git
    yum install -y gcc-c++
    yum install -y python-devel
    
Install Flask and dataset

    easy_install Flask
    easy_install dataset
    exit
    
Clone the repo

    git clone https://github.com/maxattax97/purdue-ctf.git
    cd purdue-ctf/
    
Import the tasks

    python task_import.py
    
Start the server

    python server.py

*Note*: Flask should run on top of a proper web server if you plan to have many players.

Some deployment steps are also provided for ArchLinux on the [wiki](https://github.com/balidani/tinyctf-platform/wiki/Installation-on-ArchLinux).  
Some deployment steps are also provided for Fedora Server on the [wiki](https://github.com/balidani/tinyctf-platform/wiki/Installation-on-Fedora-Server-26).  
Some deployment steps are also provided for Ubuntu Server on the [wiki](https://github.com/balidani/tinyctf-platform/wiki/Installation-on-Ubuntu-Server-17.04).

Caveats
-------

* CSRF is currently not addressed
* The platform does not support tasks with the same score and category right now
