# Install Virtual machines

Oracle VirtualBox
```
$ wget -q https://www.virtualbox.org/download/oracle_vbox_2016.asc -O- | sudo apt-key add -
$ sudo add-apt-repository "deb [arch=amd64] http://download.virtualbox.org/virtualbox/debian $(lsb_release -cs) contrib"
$ sudo apt update -y
$ sudo apt upgrade -y
$ sudo apt install virtualbox-6.0
```
