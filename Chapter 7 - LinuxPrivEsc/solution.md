# SANS HOLIDAY HACK 2023: SimonCypherSays Report
## Chapter 7 Challenge: LinuxPrivEsc
### Location: Island of Misfit Toys / Ostrich Saloon
When I see the words Linux, Privilege and Escalation in the same sentence, I have to switch from hot chocolate to peppermint mocha coffee. The excitement of attempting to elevate my privileges into a system is what I live for in CTF challenges.
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%207%20-%20LinuxPrivEsc/Chapter7-0.png)

Opening the challenge we are presented with a prompt, giving us clues to how we are going to complete the challenge. Some of the clues the prompt gives us are:

1.  Start in the land of bash, where you reside
2.  To root you must glide
3.  There lies a gift, in the root’s domain
4.  An executable file to run.

![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%207%20-%20LinuxPrivEsc/Chapter7-1.png)

To start the challenge, we will use the ```ls``` command to see what we have in our directory.
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%207%20-%20LinuxPrivEsc/Chapter7-2.png)

All we have in the current directory is the HELP file that gives us the prompt when we first open the challenge. There is a lower-hanging fruit technique we can leverage that can help us identify if we can traverse backwards in the current directory. Let’s ask ChatGPT about traversing backwards in a directory using Linux terminal.
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%207%20-%20LinuxPrivEsc/Chapter7-3.png)

Let's use ChatGPT’s suggestion of using ```cd ../../``` command to traverse backwards, followed by the ```ls``` command.
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%207%20-%20LinuxPrivEsc/Chapter7-4.png)

We successfully achieved directory traversal that enabled us to view objects in the root domain. In the HELP file, or the prompt we are given when opening the challenge for the first time, we can identify the following.

1.  To root you must glide - A root folder is visible in the root domain
2.  There lies a gift, in the root’s domain - There must be an executable file as indicated in clue #4 An executable file to run.

Let’s try to access the root folder by using the ```ls -l root``` to view the permissions of the file.
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%207%20-%20LinuxPrivEsc/Chapter7-5.png)

We clearly do not have the permissions to open or read the root folder. How do we who we are as a user in Linux terminal? In previous challenges I have done, we can user the commands ```whoami``` and ```groups username``` to find out who we are.
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%207%20-%20LinuxPrivEsc/Chapter7-6.png)

We are username: **elf** in the user group **elf**. So, where do we go from here? Well, we already traversed to the root directory and identified several folders we can explore. The first clue we were given in the prompt was “Start in the land of bash, where you reside”Start in the land of bash, where you reside”. 
Let’s ask ChatGPT what bash is?
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%207%20-%20LinuxPrivEsc/Chapter7-7.png)

We know now that bash is a command process that runs in a text window that uses commands to cause actions. Commands like ls or cd or whoami use bash to execute. Now let’s ask where to find bash in ChatGPT?
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%207%20-%20LinuxPrivEsc/Chapter7-8.png)


We know that bash shell starts by default. Now let’s ask where we can find bash in the list of folders.
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%207%20-%20LinuxPrivEsc/Chapter7-9.png)


The answer we are given is bash can be found in the directory ```/bin/bash```. In the root directory, we can see a folder named **bin**. Let’s change the directory by using the ```cd bin``` command and list all of the items in the bin folder using the ```ls``` command.
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%207%20-%20LinuxPrivEsc/Chapter7-10.png)

Inspecting the contents of the bin folder, we can see bash exists. Bash is not a directory, but a binary executable for running commands. Reading through the list, we can see familiarly binary executables such as fin, env, perl, users etc. However, what stands out from the list of binary executables are there are items highlighted in red.
1.  chfn
2.  chsh
3.  gpasswd
4.  mount
5.  newgrp
6.  passwd
7.  simplecopy
8.  su
9.  umount

Using the SANS Holiday Hack hints, we are directed to the following page: https://payatu.com/blog/a-guide-to-linux-privilege-escalation/

To summarize, we can leverage exploiting **SUID executables** where we can execute files with permissions of a specified user. There is a possibility that some of the executables may have permissions that allow us to read, write or execute commands that we normally should not have. We will start with the list that is highlighted in red to determine what permissions we have relating to these binary executables.
We will use the ```ls -l filename``` command.
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%207%20-%20LinuxPrivEsc/Chapter7-12.png)


We identified that the command simplecopy gives us read, write and executable permissions in the Linux terminal. This is a good sign because we can copy files that we would normally not have permissions to access.

Where do we go from here? Well, we used a basic directory traversal technique to find the root domain and we found a list of executables that we can use to complete this challenge in the /bin folder. The objective we have is to escalate our privileges to gain access to the root folder by moving up the ladder to obtain the root user permission. Let’s ask ChatGPT where we can find a list of users in Linux terminal.
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%207%20-%20LinuxPrivEsc/Chapter7-13.png)


In the list of folders in the root domain, we do know there is a folder called etc. Let’s travel to that folder in the directory using ```cd ../etc/``` followed by ```ls``` to list out the items in the directory.
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%207%20-%20LinuxPrivEsc/Chapter7-14.png)

Reading through the files in the directory, we can see a file that ChatGPT identified for us as passwd. We will concatenate the file by using ```cat passwd```.
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%207%20-%20LinuxPrivEsc/Chapter7-15.png)


BINGO! Now we found some very useful information in the passwd file. Let’s break this down by copying and pasting a line item into ChatGPT to help us break down what this information is.
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%207%20-%20LinuxPrivEsc/Chapter7-16.png)

Here is what we identified with ChatGPT:
Username: elf
Password: x, this placeholder informs us the password is stored in a hash in the /etc/shadow file.
UserID: 1000
GroupID: 1000
Home directory: /home/elf
Looking at the root user, we see something very similar
Username: root
Password: x, this placeholder informs us the password is stored in a hash in the /etc/shadow file
UserID: root
GroupID: 1000

So, what do we do with this information you ask? What if we are able to manipulate the passwd file? What if there is a **binary executable** that will allow us to manipulate the file? Let’s check the permissions of the file using ```ls -l passwd```.
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%207%20-%20LinuxPrivEsc/Chapter7-17.png)

Oh no!!! Unfortunately we do not have the permissions to write or execute to the file. How we know this is based off of ChatGPT’s explanation when we copied and pasted the response for identification.
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%207%20-%20LinuxPrivEsc/Chapter7-18.png)

All is not lost in this part of the challenge. Remember, we do have permissions to execute the binary executable **simplecopy**. What if we copy the file to a folder where we have the permissions to read and write to the file? Where can we copy the file to? We would need to assume that the ```/etc/``` folder only has root permissions to read, write and execute. However, we know the elf home directory and the location. We may have the permissions to read, write and maybe execute files in the home directory. Let’s use ```simplecopy`` to copy the passwd file by using the following command: ```simplecopy passwd ../home/elf/passwd```
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%207%20-%20LinuxPrivEsc/Chapter7-19.png)

Okay, this is good as we received no error in a response. Lets change directory to our home directory using ```cd ../home/elf``` followed by the ```ls``` command.
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%207%20-%20LinuxPrivEsc/Chapter7-20.png)

Hallelujah! We successfully used simplecopy to copy a file to our home directory. Now, we will assume we can manipulate the file as we are in our home directory. We need a command that will allow us to change any of the parameters of either the root user or the elf user. What binary executable can we use to manipulate the file?

Remember when we were in the land of bash, where we had a list of binary executables we can use in the Linux terminal? This took a lot of research with ChatGPT to identify what each executable does. I probably spent about one hour going through the list finding out which one would be the most suitable for the challenge. I came across the ```sed``` binary executable.
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%207%20-%20LinuxPrivEsc/Chapter7-21.png)

To help complete this challenge, I used the following URL links:
https://phoenixnap.com/kb/linux-sed
https://www.geeksforgeeks.org/sed-command-in-linux-unix-with-examples/
So, what can we manipulate in this file to elevate our privileges? Let’s look at the password file again.
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%207%20-%20LinuxPrivEsc/Chapter7-15.png)

Here is what we know, each user is assigned a userID number and a groupID number and each user has an x, indicating a password hash in the ```/etc/shadow``` file. There is another command in linux called su or switch user. We can attempt to try to switch to the root user’s account using ```su root`` for the command.
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%207%20-%20LinuxPrivEsc/Chapter7-22.png)
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%207%20-%20LinuxPrivEsc/Chapter7-23.png)

Ah-ha!!! Another useful clue!!! We can see we cannot access the root user by using the switch user command because we do not know the user’s password. Although in the passwd file, we do know the password is stored in a hash in the /etc/shadow file, we would need to assume the root user has configured the system to now allow read or write access to the file. If we were given access to read and write this file, then the system is not secure where we can change a root user’s password.
From where we are right now, we need to ask ourselves What if I am able to login to the root user’s account without a password?. Instead of moving to the etc/ directory to attempt to change the password hash in the shadow file, we simply remove a critical roadblock that would prompt a user for a password. Assuming we are able to manipulate the passwd file in our home directory and copy the file back to the /etc/ directory. It is worth a shot as this would be the path of least resistance to gain escalated privileges. In any CTF challenge, it is always wise to start with the path of least resistance and then work your way up.
We will use the suggested command ```sed -i ‘s/root:x:/root::/g’ password``` to replace the x placeholder with null. Once we execute the command we will use the cat command to concatinate passwd file.
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%207%20-%20LinuxPrivEsc/Chapter7-25.png)

Hallelujah again!! We can see we removed the x placeholder that points to the password hash in the shadow file. How, we need to cross our fingers and hope we can take this passwd file and copy and paste it back to the etc/ directory using the command ```simplecopy passwd ../../etc/passwd```
We need to use the ```../../``` command before ```etc/passwd``` as we need to traverse back to the root directory to move forward to the etc directory.
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%207%20-%20LinuxPrivEsc/Chapter7-26.png)

Good news! We received no errors or feedback that would raise concerns. Now, let’s cross our fingers and toes and take our last sip of peppermint mocha coffee and traverse to the etc/ directory and concatenate the passwd file.
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%207%20-%20LinuxPrivEsc/Chapter7-27.png)
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%207%20-%20LinuxPrivEsc/Chapter7-28.png)
Hallelujah!!! We successfully copied a file, manipulated a file and copied the manipulated file back to the etc/ directory. Now this is the moment of truth, we will use the ```su root``` command to see if we can bypass the prompt to type in a password to access the root user. We will follow up with ```whoami``` to see if we are successful in our attempt to elevate our privileges.
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%207%20-%20LinuxPrivEsc/Chapter7-29.png)

We did it! We are officially logged into the root users account! However, we are not done yet. We still have the following objectives to accomplish. There lies a gift, in the root’s domain, an executable file to run.

We will use the cd ```../../``` to traverse back to the root directory, followed by changing our directory to the root folder using ```cd root``` and using the ls command to list the contents of the root folder.
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%207%20-%20LinuxPrivEsc/Chapter7-30.png)

Now, all we need to do is execute the file by using the command ./runtoanswer
We are prompted with the question Who delivers Christmas presents? I typed in the most obvious answer being Santa. After checking, we are give then response of Your answer is correct!.

![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%207%20-%20LinuxPrivEsc/Chapter7-31.png)

### Additional Findings:
One of the items that I found when completing this challenge to write this report, I identified a file named ```runtoanswer.yaml``` in the ```/etc/``` directory folder. When concatenating this file, we are presented with the configuration file for the runtoanswer executable. If we did not know the answer to the question Who delivers Christmas presents? We could have identified the answer in this file.
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%207%20-%20LinuxPrivEsc/Chapter7-32.png)

The lessons learned in this challenge is when attempting to accomplish an objective, always attempt to use techniques that have the path of least resistance or start with lower hanging fruit. Oftentimes, when we do CTF’s we tend to overthink the most basic techniques and commands. When securing an environment, it is wise to start with the simplest controls of setting the permissions of your files and folders and your executables available to your users. All it takes is an incorrect configuration on a binary executable for a user to manipulate files or permissions to gain escalated privileges.
