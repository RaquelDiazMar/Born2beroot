# Born2beroot
From **[42Madrid](https://www.42madrid.com/) Cursus**, this repository goes around a __System Administration__ related exercise.

> Always remember that you are absolutely unique. Just as everyone else.  
*Margaret Mead*

## Mandatory Part 
### VirtualBox Installation
For this part, just refer to [Oracle VM VirtualBox](https://www.virtualbox.org/) and follow the instructions after downloading the virtualization product.
> Notice that @[42Madrid](https://www.42madrid.com/), there are space constraints related to this preliminary process. Then, most likely, installation through `storage/goinfre/intra_name` might be the best solution even though later on the work performed is bound to that iMac (choose carefully and learn to love it).  
> It shall be advisable to update the folder permissions: `sudo chmod 777 born2beroot_folder/`  
> Last, refer to [UTM](http://www.getutm.app) site for the virtualization software created for macOS and only for Apple platforms.

### Debian Installation
Let's go step by step for this part (if in doubt, refer to cursus project subject.pdf):
1. Download [Debian](https://www.debian.org/)
2. Open your previously installed VirtualBox:  
WARNING!: remember that subject requests setting up a server with the minimum services, which is, no graphical interface here.
    2.1. asjhdf  
    2.2.

### Sudo
1. Installation
Go to root and its environment through this command:
> $ su -  
> Password:

> $ apt install sudo

> $ dpkg -l | grep sudo. # to verify sudo was successfully installed

2. Adding user to sudo group
> $ adduser <username> sudo  
> $ getent group sudo  # to verify that the user was successfully added  
> $ reboot   
login:
Password:
> $ sudo -v.  
> [sudo] password for <username>:  # to verify sudo capability 
> $ sudo apt update   

3. Configuring sudo group requirements
> $ sudo vi /etc/sudoers.d/<filename>.  # <filename> shall not end in ~ or contain any .   
NOTE: [Vi Editor with Commands in Linux/Unix Tutorial](https://www.guru99.com/the-vi-editor.html)  
Defaults        passwd_tries=3                            # to limit authentication using sudo to 3 attempts in the event of an incorrect password;  
Defaults        badpass_message="<custom-error-message>"  # to add a custom error message in the event of an incorrect password;  

> $ sudo mkdir /var/log/sudo    # to log all sudo commands   
<~~~>  
Defaults        logfile="/var/log/sudo/<filename>"  
<~~~>  

Defaults        log_input,log_output   
Defaults        iolog_dir="/var/log/sudo"                 # to archive all sudo inputs&outputs to /var/log/sudo

Defaults        requiretty                                # to enable [TTY](https://manpages.debian.org/bullseye-backports/manpages-es/tty.1.es.html)  
Defaults        secure_path="/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/snap/bin"  # to restrict the sudo paths to the ones in the subject   
    

### SSH
1. Installing and configuring SSH   
> $ sudo apt install openssh-server   
    
> $ dpkg -l | grep ssh. # to verify succesful installation   
> $ sudo vi /etc/ssh/sshd_config  
    
Replace `13 #Port 22` with `13 Port 4242`   
and also `32 #PermitRootLogin prohibit-password` with `32 PermitRootLogin no`  
    
> $ sudo service ssh status  # to check SSH status or `systemctl ststus ssh` 
    
    


### Further references:
- [The Debian Administrator's Handbook](https://www.debian.org/doc/manuals/debian-handbook/case-study.en.html)
- 
___

## Bonus Part



----
Extra references:  
<https://www.42madrid.com/>  
<https://www.markdownguide.org/>
