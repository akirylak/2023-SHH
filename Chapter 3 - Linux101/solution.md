# SANS HOLIDAY HACK 2023: SimonCypherSays Report
## Chapter 3 Challenge: Linux 101
### Location: Christmas Island / Santa’s Surf Shack
After the intense snowball fight, I made my way to the otherside of the island to warm up from the intense snowball fight in Santa’s Surf Shack. Then again, we are on an island just north of the equator. How did they bring snow all the way down here?
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%203%20-%20Linux101/Chapter2_santasurfshack.png)
**Ginger Breddie** gave an introduction about this being all about Linux commands. Opening up the Linux 101 shell terminal, I am taken back by my days starting off on CTF challenges. Although this is a very basic challenge to complete, for those who may be beginners to a CTF challenge, I took the approach as if I was a novice pentester on how to solve this challenge.

## Solving the Challenge
When solving all prompts in this challenge, we will be using Linux Commands. All Linux commands are case-sensitive. We will not be using the command hintme and leverage ChatGPT for solutions

**Type ```yes``` in the prompt to begin.**

![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%203%20-%20Linux101/Chapter2-0.png)

**Perform a directory listing of your home directory to find a troll and retrieve a present!**
Solution: Directory listings can be performed by using the command ```ls```

![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%203%20-%20Linux101/Chapter2-2.png)

**Now find the troll inside the troll.**
Solution: To print out the contents of the file troll_19315479765589239, we can use the ```cat [filename]``` command.

![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%203%20-%20Linux101/Chapter2-4.png)

**Great, now remove the troll in your home directory.**

Solution: To remove a file, we will use the ```rm [filename]``` command.
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%203%20-%20Linux101/Chapter2-5.png)

**Print the present working directory using a command.**
ChatGPT Research: Ask ChatGPT “Print working directory in Linux terminal.”
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%203%20-%20Linux101/Chapter2-7.png)

Solution: Use the command ```pwd``` to print the directory.
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%203%20-%20Linux101/Chapter2-8.png)

**Good job but it looks like another troll hid itself in your home directory. Find the hidden troll!**

ChatGPT Research: See screenshot below
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%203%20-%20Linux101/Chapter2-10.png)

Solution: Use command ```ls -a``` to display all files including hidden directories. Hidden directories or files begin with a ‘.’
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%203%20-%20Linux101/Chapter2-11.png)

**Excellent, now find the troll in your command history.**

 ChatGPT Research: Ask ChatGPT “Command history Linux”
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%203%20-%20Linux101/Chapter2-12.png)

Solution: Use the ```history``` command.
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%203%20-%20Linux101/Chapter2-13.png)

**Find the troll in your environment variables.**

ChatGPT Research: Ask ChatGPT “How to view environmental variables in Linux”
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%203%20-%20Linux101/Chapter2-14.png)

Solution: Use ```env``` command.
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%203%20-%20Linux101/Chapter2-15.png)

**Next, head into the workshop.**

Solution: Use 2 commands to complete this challenge ```ls``` to list the items in the current directory and ```cd``` workshop to move or change directory access to the workshop directory.

![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%203%20-%20Linux101/Chapter2-17.png)

**A troll is hiding in one of the workshop toolboxes. Use "grep" while ignoring case to find which toolbox the troll is in.**

Research: We will use the ```ls``` command to list all files in the workshop directory.

![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%203%20-%20Linux101/Chapter2-18.png)

**Observation**: there are many files by the name ```toolbox_[filenumber].txt.``` It would be very tedious to go through each file to find the troll. The prompt hints at the term ```grep``` with ‘ignore-case’ to find the troll in the land of toolboxes.

ChatGPT Research: Ask ChatGPT “how to use grep with ignore-case.”
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%203%20-%20Linux101/Chapter2-19.png)

Solution: Because we are looking to search for a troll in all files, and all of the files are ‘.txt’ files, we will use linux command ```grep -i “troll” *.txt ```
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%203%20-%20Linux101/Chapter2-20.png)

**A troll is blocking the present_engine from starting. Run the present_engine binary to retrieve this troll.**

Research: To run a binary file, simply use the command ```./present_engine```
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%203%20-%20Linux101/Chapter2-21.png)


ChatGPT Research: The permission denied response indicates we do not have the permissions to execute a file. We will copy and paste the bash response into ChatGPT.
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%203%20-%20Linux101/Chapter2-22png)

Research: Check file permissions using ```ls -l present_engine```
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%203%20-%20Linux101/Chapter2-23.png)

ChatGPT Research: Now lets ask “how to change the file permissions to execute a file”
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%203%20-%20Linux101/Chapter2-24.png)

Assuming we have permissions to change file permissions, we will perform this in 3 steps: Change file permissions with```chmod +x ./present_engine```
Check permissions
Rerun the binary with ```./present_engine```
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%203%20-%20Linux101/Chapter2-25.png)

Solution: With the file having the x or executable permissions, we can rerun ```./present_engine```
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%203%20-%20Linux101/Chapter2-26.png)

**Trolls have blown the fuses in /home/elf/workshop/electrical. cd into electrical and rename blown_fuse0 to fuse0.**

Solution 1: Use ```cd``` command and use the /home/elf/workshop/electrical path to move to the electrical directory.
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%203%20-%20Linux101/Chapter2-27.png)

ChatGPT Research: ask ChatGPT how to rename a file.
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%203%20-%20Linux101/Chapter2-28.png)

Solution 2: use ```mv blown_fuse0 fuse0``` to rename the file.
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%203%20-%20Linux101/Chapter2-29.png)

**Now, make a symbolic link (symlink) named fuse1 that points to fuse0**
ChatGPT Research: Ask ChatGPT “What is symlink Linux command?”
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%203%20-%20Linux101/Chapter2-30.png)

Solution: Use ```ln -s fuse0 fuse1``` command.
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%203%20-%20Linux101/Chapter2-31.png)

**Make a copy of fuse1 named fuse2.**

Solution: This is a simple copy command cp with the old file name and new file name.
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%203%20-%20Linux101/Chapter2-32.png)
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%203%20-%20Linux101/Chapter2-33.png)

**We need to make sure trolls don't come back. Add the characters "TROLL_REPELLENT" into the file fuse2.**

ChatGPT Research: We ask ChatGPT, “How to add characters to a file?”
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%203%20-%20Linux101/Chapter2-34.png)

Solution: Use command ```echo “TROLL_REPELLENT” >> fuse2```
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%203%20-%20Linux101/Chapter2-35.png)


**Find the troll somewhere in /opt/troll_den.**
ChatGPT Research: Ask ChatGPT, “How to find a file in a directory?”
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%203%20-%20Linux101/Chapter2-36.png)

Solution: There are several different options for us to choose. We will use  ```find /opt/troll_den =iname "troll"``` as we are uncertain if the word “troll” is case sensitive. The solution prints all files in the directory.
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%203%20-%20Linux101/Chapter2-36_2.png)

**Find the file somewhere in /opt/troll_den that is owned by the user troll.**
ChatGPT Research: ask ChatGPT “How to find a file owned by a user?”
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%203%20-%20Linux101/Chapter2-37.png)

Solution: Use the Linux command  ```find /opt/troll_den -user troll``` to print out files owned by troll.
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%203%20-%20Linux101/Chapter2-38.png)

**Find the file created by trolls that is greater than 108 kilobytes and less than 110 kilobytes located somewhere in /opt/troll_den.**

ChatGPT Research: Use ChatGPT to ask “How to find a file by file size?”
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%203%20-%20Linux101/Chapter2-39.png)

Solution: Looking at the text in the prompt, a file that is greater than 108 kilobytes and less than 110 kilobytes must be 109 kilobytes. Use the command ```find /opt/troll_den -size 109k``` in the terminal.
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%203%20-%20Linux101/Chapter2-40.png)

**List running processes to find another troll.**
ChatGPT Research: Ask ChatGPT “How to list running processes in Linux?”
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%203%20-%20Linux101/Chapter2-41.png)

Solution: Use the ```ps aux``` command in the terminal.
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%203%20-%20Linux101/Chapter2-42.png)

**The 14516_troll process is listening on a TCP port. Use a command to have the only listening port display to the screen.**
ChatGPT Research: Ask ChatGPT “How to display listening TCP ports in Linux?”
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%203%20-%20Linux101/Chapter-43.png)
Solution: Use command ```netstat -tupnl```. Although ChatGPT recommends -tuln, from experience we can add the command -p to include the process ID in the response
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%203%20-%20Linux101/Chapter2-43_2.png)
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%203%20-%20Linux101/Chapter2-44.png)

**The service listening on port 54321 is an HTTP server. Interact with this server to retrieve the last troll.**
Solution: The ```curl``` command allows us to retrieve the contents of the HTTP server. Because this is an HTTP server with port54321 and we do not have a URL listed in the prompt, we are going to assume this service is on the localhost. Use command ```curl http://localhost:54321```

![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%203%20-%20Linux101/Chapter2-45.png)

**Your final task is to stop the 14516_troll process to collect the remaining presents.**

ChatGPT Research: Ask ChatGPT, “How to stop a process in Linux terminal”?”
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%203%20-%20Linux101/Chapter2-46.png)


Solution: There are two steps to the process. We need to use the command ```pgrep 14516_troll``` to get the process ID name or (PID) of the process. Once we have the PID number, we can use the number with the Linux command ```kill 1780``` to stop or kill the process.
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%203%20-%20Linux101/Chapter2-47.png)

**Ending: Congratulations, you caught all the trolls and retrieved all the presents! Type "exit" to close…**


The Linux 101 challenge was a great warmup and refresher of the basic Linux commands all users should know. After the completion of the challenge, there were no further actions needed on this island. I decided to head back to the ship and do a bit of exploring around Christmas Island to see if there were other ports to dock and complete more challenges.
