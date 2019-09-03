# Install RITA on Your Personal Computer
[RITA repository link](https://github.com/activecm/rita)

This file contains directions for how to [manually install RITA](https://github.com/activecm/rita/blob/master/docs/Manual%20Installation.md) on your personal computer. We recommend that you complete the installation on your own and only use this guide as a reference when needed. This tutorial is done using a MacOSX operating system. 

---

### Download Dependencies:
In order for RITA to work, we must first install BRO/ZEEK and MongoDB V3.6. Then for RITA to compile, we have to install Golang and Dep. Finally, we will need to create public/private SSH keys to download RITA from Github. 

Open up your terminal window. 

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

#### [Download Golang](https://golang.org/doc/install)
1. To download Golang, download the [binary file](https://golang.org/dl/). 
    - If installed, the package will be put in     `/usr/local/go/bin`. You can find `/usr` by typing `cd ..` and `ls` in the terminal window until you see the `usr` folder. To check if installed type `ls /usr/local/go/bin` and you will see *go*.
    
2. Once installed, follow the instructions under *Installing Golang* within the [Install Rita Manually Documentation](https://github.com/activecm/rita/blob/master/docs/Manual%20Installation.md). 
    - Create a local GO development environment: `mkdir -p $HOME/go/{src,pkg,bin}`
    - Add command lines into your *.bashrc* file as described in step 3:
      - `echo 'export GOPATH="$HOME/go"' >> $HOME/.bashrc`
      - `echo 'export PATH="$PATH:$GOPATH/bin"' >> $HOME/.bashrc`
      - `source $HOME/.bashrc`

To check if the command lines have been added, type `vim .bashrc` to open up the file. If done properly, you should see `export GOPATH="$HOME/go"` and `export PATH="$PATH:$GOPATH/bin"` within the file. To exit, type `:exit`. 
    
#### [Download Dep](https://golang.github.io/dep/docs/installation.html)
1. Follow the simple instructions:
    - `brew install dep`
    - `brew upgrade dep`

#### Generate Public/Private SSH Keys
1. Generate an ssh key: `ssh-keygen -t rsa`
2. Press *enter* to accept the default location. The `ssh-keygen` utility prompts you for a passphrase.
3. Type in a passphrase. You can also hit the *enter* key to accept the default (no passphrase). However, this is not recommended.

Your private key is saved to the *id_rsa* file and your public key is saved to the *id_rsa.pub* file within the *.ssh* directory. You can check for your private and public key by typing in `cd .ssh` then `vim id_rsa` to view your private key and `vim id_rsa.pub` to view your public key. 

In order to access git, we need to add these keys within the *.gitconfig* file. Note that if you do not have a GitHub account, you will need to create one. Once created, subsititue *HackerGirl* for your username and *hackergirluniversity@gmail.com* for your email.
- `git config --global user.name "HackerGirl"`
- `git config --global user.name "hackergirluniversity@gmail.com"`

Finally, in your github account on the top right, click on your icon and go into settings. From settings, select *SSH and GPG Keys* and click *New SSH Key*. Copy and paste the key from the `id_rsa.pub` file into here and be sure to include *ssh-rsa* when copying over. 

---

### [Download RITA](https://github.com/activecm/rita/blob/master/docs/Manual%20Installation.md):
At this point, we are now ready to build RITA! For this tutorial, we are going to practice installing RITA manually to strengthen our operations within the DevSecOps Curriculum. 

#### Building RITA
Under *Building RITA*, we follow the instructions. 
- `git clone git@github.com:activecm/rita.git`
- `cd go/src/github.com/activecm/rita`
- `sudo make install`



