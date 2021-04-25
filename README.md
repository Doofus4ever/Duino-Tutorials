                                                INSTALL DUINO CLUSTER WORKER ON IPHONE
					                        BY Doofus4ever
										 
**DISCLOSURE**
									 
Firstly thank you for taking the time to read this document i will explain how i got Duino-Coin miner running on my iphone
please note this is the cluster worker i got running on the Iphone. Full disclosure i am not responsible for any damages
caused to your iphone if u decide to mine with any iphone/android phone make sure you take off any phone covers you have to 
allow the heat to dissapate and put a fan near the phone to cool it. Before you continue make sure you have the cluster server
running on your network so the Iphone can find it.



**APP THAT CAN RUN LINUX ON YOUR IPHONE**

Right down to brass and tacks first head to the app store and download an app called iSH it runs Alpine Linux on it thats 
how we going to get it up and running now before you say "yay" and type apt install..... Alpine Linux uses apk add (package 
name) to install programs/dependencies. Alpine Linux does not have python 3 installed so we have to install it manually

**INSTALL PYTHON3**

first create a folder by using command "mkdir python3" (note u dont have to use sudo) after that type "cd python3" to enter
the folder u created next type "apk add wget" to install wget so u can download the files from the internet next type this long command that downloads the files for python3 from github and add to repo list:
wget -qO- http://dl-cdn.alpinelinux.org/alpine/v3.12/main/x86/apk-tools-static-2.10.5-r1.apk | tar -xz sbin/apk.static && ./sbin/apk.static add apk-tools && rm sbin/apk.static
after it finishes doing its thing that you will be able to install python3 using command "apk add python3" when its done yay
you have installed python3 next install gcc compiler "apk add gcc" next install python3-dev type "apk add python3-dev"

**INSTALL PIP SO YOU CAN RUN PIP COMMANDS**

to install pip you type... no not apk add python3-pip3 it will give you an error instead use command "apk add py3-pip"
Yay you have installed pip3

**UPGRADE ALPINE**

Like any linux distro you have to update it type "apk update" when its done type "apk upgrade"

**INSTALL GIT AND NANO**

To clone the github duino cluster page you need to install git by using command "apk add git" then its a good idea to 
install a text editor i use nano "apk add nano"

**ALMOST THERE...**

Next we need to install dependencies for the duino cluster worker miner so it can work first install wheel it will install
the latest dependencies or else pip3 will install legacy dependencies type "pip3 install wheel" ignore any red error texts.
next install dependencies py-cpuinfo, colorama, requests, pyserial, pypresence, tronpy, cryptography all using command
"pip3 install (PACKAGE NAME)" once you have done this. we need to type "cd" to go to root directory now we have to clone the 
github page of the cluster miner type "git clone https://github.com/DoctorEenot/DuinoCoin_cluster.git" after that type 
"cd DuinoCoin_cluster" to enter the file next type "nano cluster_worker.py" and delete out line 2 that says "xxhash" 
next scroll down till u find the line that has:
CLUSTER_SERVER_ADDRESS = ('192.168.1.2',9090) replace the ip address with the ip your sever is running on, WORKER_NAME = 'TEST'
you can change it to your device name although you dont have to. Press ctrl and s to save then ctrl and x to exit the editor

**AT LAST!!**

Now just type "python3 cluster_worker.py" and give it a couple of seconds Bingo its mining if you made it to the end give 
yourself a pat on the back you did it you have duino mining on your Iphone

**Before you go...**

If you liked this document please send a small Duino-Coin donation any amount will be appreciated send Duino-Coin Donations to: Doofus4ever
