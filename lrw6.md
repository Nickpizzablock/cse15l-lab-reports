# **Lab Report Week 6**
#### Written by Neo Torres

Links:
[Homepage](https://nickpizzablock.github.io/cse15l-lab-reports/)

## Streamlining ssh Configuration
I editied my .ssh/config file so it is easier to log into ieng6. Here are my steps...
<!-- Add a picture of -->

### Editing .ssh/config 
1. Navigate to your .ssh folder. For windows, it is usually under C:\Users\(your device name)\.ssh

2. Right click an empty part of the folder and click "Open with Code".

3. Make a new file named conifg if there isn't one alreadt (no extension).

4. In the file, type in the following lines.

```

```

(a) after host should be replaced with your nickname of choice. Mines `ieng`.
(b) after ostname should be the IP or domain of the server. In this case, its `ieng6.ucsd.edu`.
(c) after user should be your username. Mines `cs15lwi22aqu`.
(d) after IdentifyFile is the ssh file that automatically inputs your password for you. Typically its `~\.ssh\id_rsa`

Remember, Linux based operating systems use / while windows use \.


### Demonstration of ssh working

Now, all I have to do is type `ssh ieng` and input my local ssh password to get into ieng6.

Tadaaaaaaa

### Demonstration of scp working

I can also send a file over to ieng6 with the shortcut.
I'm going to send a text file over using the command `scp example.txt ieng`.

YAY!