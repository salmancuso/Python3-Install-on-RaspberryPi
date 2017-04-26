# Python 3 Install on RaspberryPi

The in of this repository is to provide a guideline for installing Python 3 on a Raspberry Pi or any Debian/Ubuntu based Linux machine. 

There are four sections.  The first will install dependencies that python 3 will need. The second is the instantiation of Python 3. The third will install pip3. Finally, we will make Python 3 our default python on our machine.

Why will I make Python 3 my default on my system vs. Python 2?  For the majority of my coding life I've worked in Python 2, it is comfortable, easy to use and let's face it there has been an abundance of libraries.  That said in the year 2020 (which is less than three years from the time I am wrighting this) Python 2 will be discontinued and support (upgrades and patches) will cease. 

# INSTALL DEPENDENCIES 
  ```
  sudo apt-get install libbz2-dev liblzma-dev libsqlite3-dev libncurses5-dev libgdbm-dev zlib1g-dev libreadline-dev libssl-dev tk-dev
```

# DOWNLOAD, BUILD AND INSTALL PYTHON 3.
  ### NOTE. CHANGE 3.6.1 TO THE RELEASE YOU WANT
```
mkdir ~/python3
```
```
  cd ~/python3  
```
```
  wget https://www.python.org/ftp/python/3.6.1/Python-3.6.1.tar.xz
```
```
  tar xvf Python-3.6.1.tar.xz
```
```
  cd Python-3.6.1
```
```
  ./configure
```
```
  make
```
```
  sudo make install
```
```
  sudo rm -rf ~/python3/Python-3.6.1
```
```
  sudo reboot
```
# INSTALL PIP3
```
  sudo apt-get install python3-pip
```

# CHANGE PYTHON 3 TO BE DEFAULT PYTHON.
  ### THIS ASSUMES YOU ALREADY HAVE PYTHON2.7 INSTALLED ON YOUR SYSTEM
  ```
  sudo update-alternatives --install /usr/bin/python python /PATH/TO/PYTHON3 1
  
  sudo update-alternatives --install /usr/bin/python python /PATH/TO/PYTHON2.7 10
  
  sudo update-alternatives --config python
```
### This last command will allow you to choose which version of python to use by default. For me I had to select #2 as the default. Lastly reboot the system. 

