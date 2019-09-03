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

#### [Download MongoDB 3.6](https://docs.mongodb.com/v3.6/administration/install-community/)
Note that RITA reccomends using "MongoDB version is 3.6, but anything >= 3.2.0 and < 3.7.0 should work." To install MongoDB 3.6 follow these [installation instructions](https://docs.mongodb.com/v3.6/administration/install-community/). Now if you have MongoDB 4.2 installed, you have to follow these [downgrade instructions](https://docs.mongodb.com/manual/release-notes/4.0-downgrade-standalone/). 
1. To download MongoDB 3.6, we must install the required dependencies:
    - To add the MongoDB formula repository: `brew tap mongodb/brew`.
2. To download MongoDB 3.6:
    - `brew install mongodb-community@3.6`.    
