# Install RITA on Your Personal Computer
[RITA repository link](https://github.com/activecm/rita)

This file contains directions for how to [manually install RITA](https://github.com/activecm/rita/blob/master/docs/Manual%20Installation.md) on your personal computer. We recommend that you complete the installation on your own and only use this guide as a reference when needed. This tutorial is done using a MacOSX operating system. 

---

### Download Dependencies:
In order for RITA to work, we must first install BRO/ZEEK and MongoDB. Open up your terminal window. 
#### [Download BRO/ZEEK](https://docs.zeek.org/en/stable/install/install.html)
1. To download BRO/ZEEK, we must install the required dependencies: 
    - To compile source coude on MAC, we need to install XCODE: `xcode-select -p`.
    - If you do not have Homebrew installed on your machine, install [Homebrew](https://brew.sh/).
    - We then need the following dependencies: `cmake`, `swig`, `openssl`, and `bison`. To install these packages, use the command `brew install [package name]`. For example use `brew install cmake` to install the `cmake` dependency. 
2. Now to download BRO/ZEEK follow the instructions under *Installing from Source* and be sure you are in the `zeek` directory.
    - `git clone --recursive https://github.com/zeek/zeek`
    - `./configure`
    - `make`
    - `make install`
    - If you run into any administrative issues, run the command `sudo make` or `sudo make install`. By using `sudo` you are forcing the ability of running commands at the root level of your computer's operating system. 

#### [Download MongoDB V3.6](https://docs.mongodb.com/v3.6/administration/install-community/)
Note that RITA reccomends using "MongoDB version is 3.6, but anything >= 3.2.0 and < 3.7.0 should work." To install MongoDB 3.6 follow these [installation instructions](https://docs.mongodb.com/v3.6/administration/install-community/). Now if you have MongoDB 4.2 installed, you have to follow these [downgrade instructions](https://docs.mongodb.com/manual/release-notes/4.0-downgrade-standalone/). 
1. Install the required dependencies: `brew tap mongodb/brew`.
2. To download MongoDB V3.6: `brew install mongodb-community@3.6`.    

Let's take a note of the following comment "Ensure MongoDB is running before running RITA." To run MongoDB, run these commands:
- `mongod --config /usr/local/etc/mongod.conf`
- `Mongo`

---

### [Download RITA](https://github.com/activecm/rita/blob/master/docs/Manual%20Installation.md):
For this tutorial, we are going to practice installing RITA manually to strengthen our operations within the DevSecOps Curriculum. In the directions, it says that in order to compile RITA, we need to install both Golang and Dep.

#### [Download Golang](https://golang.org/doc/install)
1. To download Golang, download the [binary file](https://golang.org/dl/). If installed, the package will be put in     `/usr/local/go/bin`. You can find `/usr` by typing `cd ..` and `ls` in the terminal window until you see the `usr` folder. To check if installed type `ls /usr/local/go/bin` and you will see `go`.

