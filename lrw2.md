# **Lab Report Week 2**
#### Written by Neo Torres

Links:
[Homepage](https://nickpizzablock.github.io/cse15l-lab-reports/)
 

<!-- TODO:
- [!] Installing VScode
- [ ] Remotely Connecting
- [ ] Trying Some Commands
- [ ] Moving Files with scp
- [ ] Setting an SSH Key
- [ ] Optimizing Remote Running -->

## Installing VScode
1. Go to [https://code.visualstudio.com/](https://code.visualstudio.com/).
2. Click the download button appropriate for your operating system.
3. Follow through the instructions on screen.

<br>

![Image](CSE15lw2img1.jpg)

<br>

## Remotely Connecting
1. Install **OpenSSH** on Windows by going to Settings > Apps > Apps and Features > Optional features > Add a feature
2. Install **OpenSSH Client** and **OpenSSH Server**
2. Locate your **UCSD account** at [https://sdacs.ucsd.edu/~icc/index.php](https://sdacs.ucsd.edu/~icc/index.php).
3. In VSCode, use the command **Ctrl + shift + '** to open a terminal.
4. Type this in the terminal but replace zz with your account.
>ssh cs15lwi22zz@ieng6.ucsd.edu
5. Type **Yes** and then your password in the terminal to connect.
6. To close, type exit.

<br>

![Image](CSE15lw2img2.jpg)

<br>

## Trying Some Commands
* cd ~
* cd
* ls -lat
* ls -a
* ls /home/linux/ieng6/cs15lwi22/cs15lwi22zz
* cp /home/linux/ieng6/cs15lwi22zz/public/hello.txt ~/
* cat /home/linux/ieng6/cs15lwi22zz/public/hello.txt
<!-- 
cd ~;
cd;
ls -lat;
ls -a;
ls /home/linux/ieng6/cs15lwi22/cs15lwi22zz;
cp /home/linux/ieng6/cs15lwi22zz/public/hello.txt ~/;
cat /home/linux/ieng6/cs15lwi22zz/public/hello.txt;
 -->

![Image](CSE15lw2img3.jpg)
## Moving Files with scp
1. To send, go to directory of target file.
2. Type 
>scp (FileName) cs15lwi22zz@ieng6.ucsd.edu:~/
3. Put in password

<br>

![Image](CSE15lw2img4.jpg)

<br>

## Setting an SSH Key
EDIT 02/24/2024:
Super Simple Steps
>ssh-keygen # Not needed if already have key <br>
>ssh-copy-id username@serverip

1. On client side, type
>ssh-keygen 

2. Save the key to the default directory
3. Make a password and confirm
4. Open Powershell as Administrator and enter the following commands (the private key is the file without .pub)
>Get-Service ssh-agent | Set-Service -StartupType Manual <br>
>Start-Service ssh-agent <br>
>Get-Service ssh-agent <br>
>ssh-add (Directory of private key) <br>
5. Login into server and enter
>mkdir .ssh
6. Go back to client and type
>scp (directory of Public Key) cs15lwi22zz@ieng6.ucsd.edu:~/.ssh/authorized_keys

<br>

![Image](CSE15lw2img6.jpg)
##### (I put this in a Linux virtual machine because I am not sure what happens when you do ssh-keygen with a computer that already has a key)
<br>

## Optimizing Remote Running

* Writting a command in quotes will run on the server directory 
>ssh cs15lwi22zz@ieng6.ucsd.edu "ls"

* Semicolons allow for running multiple commands in the same line
>cp WhereAmI.java OtherMain.java; javac OtherMain.java; java WhereAmI

![Image](CSE15lw2img5.jpg)

The challenge is to save, upload, and execute a java file. I was able to complete the process in 9 steps by using the up arrow.

* pressed up
>scp "C:\Users\neodo\Downloads\Neo's Corner\whereAmI.java" cs15lwi22aqu@ieng6.ucsd.edu:~/

* pressed enter

* paste password

* pressed enter

* pressed up 2 times
>ssh cs15lwi22aqu@ieng6.ucsd.edu "javac WhereAmI.java; java WhereAmI"

* pressed enter

* paste password

* press enter

My time was 24 seconds. It saved time by not having to write the server name and file direcoty every time one needs to change. Having to do this manually would take a lot of work for something that can be automated. Having no password would save lots of time with less inputs.
