# SANS HOLIDAY HACK 2023: SimonCypherSays Report


## Introduction
The anticipation leading up to receiving the email notification of the 2023 SANS Holiday Hack had me on the edge of my seat as I patiently waited for the invitation to land in my inbox. On December 7, 2023 at 7:00AM EST, it finally arrived in my inbox. Although I wanted to click the **Play Now** button immediately. I had to patiently wait until the evening when I can start the challenge when I can safely and securely transform into **SimonCypherSays**: the overexcited beginner CTF competitor who tackles challenges to save the day; or in this case, help Santa before he travels the world to deliver presents to children for Christmas.


## Chapter 1 Challenge: Holiday Hack Orientation
### Location: Christmas Island
The boat ride to Christmas Island was extremely quick as I felt like I teleported from the real world into the digital world of the Geese Islands. You can say it was more like a smooth transition rather than smooth sailing. Thankfully I do not get SYN/ACK sick or sea sick.

As I approach closer to the center of the island I am greeted by an elf named **Jingle Ringford** to give me an introduction of what is to come with this year’s SANS Holiday Hack.
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%201%20-%20Orientation/Chapter1_orientation1.png)
Instructions on how to complete the first challenge were very straight forward. As a person who has completed previous CTF challenges, the objective to click on the upper panel of the terminal window and type answer and press Enter on the keyboard was very straightforward.
If completing the first challenge was this easy, I have a gut feeling, filled with Flaming Hot Cheetos and coffee that completing the challenges should be very straightforward.
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%201%20-%20Orientation/Chapter1_orientation2.png)

### Solving the Challenge
Follow the instructions in the orientation terminal to complete.


## Chapter 2 Challenge: Snowball Fight
### Location: Christmas Island / Frosty Beach
Thank you SANS for providing some directions to Frosty Beach. I am not a sailor nor would I ever be commandeering a ship. The GPS signals here are very good compared to other places I have been near an ocean.

Upon arriving on Frosty Beach, I wasn’t sure who to be excited about; meeting Santa in person or meeting a goose who wasn’t trying to chase me for a bite of my lunch. After an introduction of Santa’s operations on Geese Islands, the use of Chat NPT and an introduction to the challenge. I don’t blame Santa for taking a break and moving operations to a warmer climate. I do not live near the North Pole, yet where I am with the heat on, I wish I was near the equator around this time of year. I was recommended to speak to **Morsel Nougat** about a **Snowball Fight** and to stop by **Santa’s Surf Shack.**
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%202%20-%20Snowball%20Right/Chapter2_frostybeach1.png)
To those that are reading this report, anytime there are booths in a CTF like this, always worth checking out. Great to have as bookmarks in your browser to review later when you need a break from a CTF or if you prefer to reference them later. Very happy to see AWS is a vendor on this island.
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%202%20-%20Snowball%20Right/Chapter2_frostybeach2.png)

Navigating to the otherside of the island, I ran into Morsel Nougat. It is awesome to know that Santa and the elfs can take a break from their duties to participate in a snowball fight.
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%202%20-%20Snowball%20Right/Chapter2_frostybeach3.png)

### Solving the Challenge
Morsel gave some great pointers related to how to solve this challenge including some key words

**“Santa, some elves, and I are having a snowball fight, and we'd love you to join us. Santa's really good, so trust me when I say it's way more fun when played with other people.**

**But hey, if you can figure out a way to play solo by tinkering with client side variables or parameters to go solo mode, go for it!**

**There's also ways to make the elves' snowballs do no damage, and all kinds of other shenanigans, but you didn't hear that from me.**

**Just remember, it's all about having fun and sharing the joy of the holiday season with each other.”**

Clicking on the snowball fight, I decided to try to play the game a few times to see how the mechanics work and to have a little fun. Afterall, it was 10:00 PM, so I needed to have a little fun.
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%202%20-%20Snowball%20Right/Chapter2_frostybeach4.png)
After playing for 30 minutes, I got lucky with one other player. We were able to defeat all of the elves and defeat Santa in a snowball fight. Although it took us two tries to do it, we were able to accomplish this without needing to modify any client-side variables or parameters in the browser window. It should be noted, we were able to keep our health bar up by circling around the map to keep a safe distance from the elves and Santa. It is safe to say, it was teamwork that helped us complete the game fair and square.

### Solution Performed
Played the game with another player with the power of strategy and teamwork.

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


## Chapter 4 Challenge: Reportinator
### Location: Christmas Island /  Rudolph’s Rest
Upon arriving at **Rudolph's Rest**, I am greeted by another goose who spoke in the tone of “Honk, Honk”. Unfortunately I do not speak goose to understand a word it says. 
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%204%20-%20Reportinator/Chapter3_rudolphsrest1.png)

Following the path, I am led to the next challenge titled **Reportinator**.
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%204%20-%20Reportinator/Chapter3_rudolphsrest2.png)

The objective to completing Reportinator is to review the pentest report and identify which findings are true positives and others that are false positives. Although it could be possible to read the entire report and use ChatGPT and research to identify the false positives; it is possible that AI tools can hallucinate or give false information. Let's explore if there is another way to solve this challenge with CTF hacking.

In the Google Chrome browser, right click the **iFrame** and select **Inspect**.

Inside the Developer Tools in the Elements tab, we are going to locate and copy the **iframe src**. This source link is the challenge link with a token attached to identify us as a user for this specific challenge. We will use this link for testing purposes to inspect the link in a powerful application called Burp Suite. For this challenge we will be using the Burp Suite: free community edition.

![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%204%20-%20Reportinator/Chapter4_1.png)

Using Burp Suite, we will use the **Proxy: Intercept** module to intercept traffic for the challenge reportinator. The screenshot below displays the request when we intercept the iframe src URL.
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%204%20-%20Reportinator/Chapter4_2.png)

At the bottom of the browser window,, we will click the **Submit Review** button and investigate the traffic we are intercepting.
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%204%20-%20Reportinator/Chapter4_3.png)

After clicking the **Submit Review** button, let's check Burp Suite to investigate the traffic and response we intercepted.
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%204%20-%20Reportinator/Chapter4_4.png)

At the bottom we can see input values that are being passed into the response. Upon further investigation, I identified responses that have a **green checkbox** or that are labeled as True have a value of 0. For responses that have a **red checkbox** or that are labeled as False have a value of 1. In total, there are 9 input values that could have a value of 0 or 1.

Lets ask ChatGPT how many combinations of 0s and 1s with a character length of 9 we would need in hopes to find the correct combination to solve the challenge.
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%204%20-%20Reportinator/Report2.png)

In total there are 500 combinations of 0s and 1s we would need to modify for the input values. Although this can be performed manually, realistically this would take a great amount of time. Unfortunately, I do not have all night to manually check 500 combinations.

Let’s copy and paste these combinations into a XLS file and use the list of numbers in Burp Suite to our advantage. The screenshot below is a sample of the list of number combinations we will use to **brute force** by creating a **payload** using the **intruder** module in Burp Suite.
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%204%20-%20Reportinator/Chapter4_5.png)

In the **POST** request, we will send this request to the Intruder module by right-clicking the window and selecting **Send To Intruder**.
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%204%20-%20Reportinator/Chapter4_6.png)

Inside the Intruder module for Positions, we will select the number values 0 to format the payload attack type. In Burp Suite you can highlight the 0 values and click the Add ```§``` button for the 9 0 values you will need to select or the Auto ```§``` button to auto-select the 0 values in the input. Make sure you delete any ```§``` symbols where a payload is not needed. For the attack type, we will use **Pitchfork**.
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%204%20-%20Reportinator/Chapter4_7.png)

Why are we using a Pitchfork attack? Burp Suite provides an explanation in the drop-down.
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%204%20-%20Reportinator/Chapter4_8.png)

Because we have 9 different values that could have a combination of 0s and 1s, Pitchfork is the best way to achieve simultaneous iterations. Click on the **Payloads** tab to configure the payloads. (next to Positions). For **Payload Sets** we will configure all 9 payload sets to have the **Payload Type of Simple List**. For **Payload Settings** we will use the columns of 500 numbers (not rows), and copy and paste each column of numbers to a designated payload settings box.
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%204%20-%20Reportinator/Chapter4_9.png)

Example: For Payload Set 1 we will copy the first column of numbers in the spreadsheet. For Payload Set 2 we will copy the second column of numbers in the spreadsheet. Repeat the process for until we have all 9 columns of numbers assigned to a payload.

### BONUS!!!!!!
In the settings tab, we can configure the **Grep - Extract** option to extract a server response from the HTTP header. Click the Add button to add a response to extract.
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%204%20-%20Reportinator/Chapter4_10.png)

Click on the **Refetch Response button**. In the HTTP request, highlight **{“error”: “FAILURE”}**. Click the Ok button at the bottom of the window. Configuring a Grep - Extract response, will help us identify server responses for anomalies. Assuming a wrong answer will result in **FAILURE** the right answer should have a response of **SUCCESS**.
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%204%20-%20Reportinator/Chapter4_11.png)

Once we have the payloads set, we will click the **Start Attack** button. For the Burp Suite community edition, it does take time for the attack to finish as we are using Pitchfork to simultaneously brute force 500 different combinations of numbers. Hopefully the attack is complete by the time my hot chocolate is ready for late night consumption.

Half-way through the process of attacking or **brute forcing** payloads, we discovered in line item 247 a response that stands out. Upon closer inspection, we can see a **response** in the response tab that will return a hash value and a resource ID.
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%204%20-%20Reportinator/Chapter4_12.png)

In the Request tab, we will take note of the responses.
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%204%20-%20Reportinator/Chapter4_13.png)

Although we can go into our Chrome Browser and complete the challenge in the **iFrame** by selecting Green for values that are 0 and Red for values that are 1. We will finish this challenge in Burp Suite.

We will turn off Interception and open up a new Chromium browser window. We will sign into our 2023 SANS Holiday Hack Account and open the Reportinator challenge.

Once we are at the bottom of the report, before we click the Submit Review button, we will turn on Intercept to intercept the traffic. In the Chromium Browser, click the Submit Review button.

In the **POST** request, we will paste in the input values at the bottom. Click the **Forward** button to forward this request.
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%204%20-%20Reportinator/Chapter4_14.png)

Ta-Da!, (in reality I quoted no other than John McClane’s infamous catchphrase from Die Hard). We completed the challenge for Reportinator.
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%204%20-%20Reportinator/Chapter4_15.png)

Overall Reportinator was a great challenge to brush up and leverage Burp Suite’s tools and the power intercepting traffic for a HTTP response. This is one tool that every PenTester should have in their arsenal and every user who is interested in CTF challenges should learn to use. It should be noted that this tool is powerful and should be used responsibly. For users that would like to learn to use the tool, I recommend Portswigger academy.

## Chapter 5 Challenge: Azure 101
### Location: Christmas Island / Rudolph’s Rest
Following the path to the left, we come across our second challenge in Rudolph’s Rest titled Azure 101. There is a big crowd here tonight surrounding the challenge. I hope the majority of these users are doing just as well as I am with completing these challenges. I still wonder why I look like I have a half-melted marshmallow as a hat. Personally, I prefer to wear an aviator hat.
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%205%20-%20Azure101/Chapter5-1.png)

Opening the Azure CloudShell, we type in our first prompt to start the challenge: ```az help | less```

![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%205%20-%20Azure101/Chapter5-2.png)

We are provided a list of commands that will be useful for us to complete this challenge. The prompt gives us the next set of instructions to complete the second part of the challenge. This command is very straight forward as we will use az account show | less .

However, we need to quit the help page by using the ```q``` character to bring us back to the shell window.
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%205%20-%20Azure101/Chapter5-3.png)

**Next, you've already been configured with credentials. Use 'az' and your 'account' to 'show' your current details and make sure to pipe to less ( | less )**
Follow the instructions provided in the prompt by using ```az account show | less```
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%205%20-%20Azure101/Chapter5-4.png)
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%205%20-%20Azure101/Chapter5-5.png)

**Excellent! Now get a list of resource groups in Azure. For more information: https://learn.microsoft.com/en-us/cli/azure/group?view=azure-cli-latest**

Reviewing the documentation microsoft provides, we will use the command ```az group list | less```
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%205%20-%20Azure101/Chapter5-6.png)
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%205%20-%20Azure101/Chapter5-7.png)

Use the q character to quit and go back to the Azure shell.

**Ok, now use one of the resource groups to get a list of function apps. For more information: https://learn.microsoft.com/en-us/cli/azure/functionapp?view=azure-cli-latest**
**Note: Some of the information returned from this command relates to other cloud assets used by Santa and his elves.**

Reviewing the documentation microsoft provides, we will use the command ```az functionapp list --resource-group northpole-rg1```

![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%205%20-%20Azure101/Chapter5-8.png)
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%205%20-%20Azure101/Chapter5-9.png)

**Find a way to list the only VM in one of the resource groups you have access to. For more information:https://learn.microsoft.com/en-us/cli/azure/vm?view=azure-cli-latest**

Reviewing the documentation microsoft provides, we will use the command ```az vm list --resource-group northpole-rg2```
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%205%20-%20Azure101/Chapter5-10.png)
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%205%20-%20Azure101/Chapter5-11.png)

**Find a way to invoke a run-command against the only Virtual Machine (VM) so you can RunShellScript and get a directory listing to reveal a file on the Azure VM. For more information:**
**https://learn.microsoft.com/en-us/cli/azure/vm/run-command?view=azure-cli-latest#az-vm-run-command-invoke**

Reviewing the documentation microsoft provides, we will use the command ```az vm run-command invoke -g northpole-rg2 -n NP-VM1 --command-id RunShellScript --scripts "ls" --output table```
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%205%20-%20Azure101/Chapter5-12.png)


## Chapter 6 Challenge: Hashcat 
### Location: Island of Misfit Toys / Scaredy Kite Heights
After completing all of the challenges on Christmas island, with the exception of the final challenge in the **Resort Lobby**, I decided to hop on the ship and venture off and explore the four remaining islands. Upon my arrival on the Island of Misfit Toys, I am greeted by the Goose of the **Island of Misfit Toys**. I have a strong feeling there is some relationship between these geese and a future challenge of the game.
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%206%20-%20Hashcat/Hashcat0-goose.png)

Venturing off deep into the island, I come across my first challenge on the island: **Hashcat**. I have a very strong feeling before starting the challenge that we will be using password hashes and password lists.

![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%206%20-%20Hashcat/Hashcat0-1.png)

The introduction text provides us with all of the clues we need to complete this challenge. We can leverage ChatGPT to help us complete the challenge by identifying the best Linux commands to use.

![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%206%20-%20Hashcat/table1.png)
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%206%20-%20Hashcat/table2.png)
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%206%20-%20Hashcat/table3.png)
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%206%20-%20Hashcat/table4.png)

Before we get started on using Hashcat, we need to explore our terminal environment to see what files are available to us to leverage. We will use the Linux command ```ls``` to see if there are files in the directory.
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%206%20-%20Hashcat/Hashcat0-7.png)

Let's explore what is inside hash.txt by concatenating with the ```cat``` command.
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%206%20-%20Hashcat/Hashcat0-8.png)

In the beginning of the hash, we can see ```$krb5asrep``` as the first 10 characters of the hash. This is the ASREP hash that contains the password. Now, let’s explore what is inside ```password_list.txt``` by concatenating with the ```cat``` command.
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%206%20-%20Hashcat/Hashcat0-9.png)

We can see a list of potential passwords in the form of a word list to perform a dictionary attack using hashcat. To start with our attempt with cracking the hash.txt file, we will start with the following command: ```hashcat -a 0 -m 18200 hash.txt password_list.txt```.
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%206%20-%20Hashcat/table5.png)

In Linux terminal, you can view all of the available commands by typing in ```hashcat -h```, however due to limitations with the size of the window, it is best to reference the wiki page.

Our starting command gave us the following response:
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%206%20-%20Hashcat/Hashcat0-10.png)

The response provided us a recommendation to use the ```--force``` option in our hashcat command.
We will update our command using: ```hashcat -a 0 -m 18200 --force hash.txt password_list.txt```.
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%206%20-%20Hashcat/Hashcat0-11.png)


Unfortunately the second command was aborted due to the process taking too long to complete. Although we can switch to optimized OpenCL kernels by using the ```-O``` command. This will provide the same response as we see in the screenshot above. However, in the introduction text of the challenge, we are given hints to commands we can use: ```-w 1 -u 1 --kernel-accel 1 --kernel-loops 1```

Let’s use the wiki page to identify what these commands that are provided to us are.
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%206%20-%20Hashcat/table6.png)
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%206%20-%20Hashcat/table7.png)

Because ```--kernel-loops 1``` is the same as ```-u 1```, we will favor the use of ```-u 1``` in our next command. The same will go for ```--kernel-accel 1``` and ```-n 1```. Let’s modify our command to leverage ```-w```, ```-u``` and ```-n``` commands: ```hashcat -a 0 -m 18200 -w 1 -u 1 -n 1 hash password_list.txt```
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%206%20-%20Hashcat/Hashcat0-15.png)
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%206%20-%20Hashcat/Hashcat0-16.png)

Finally, with some trial and error, and discovery, we have a status update! We identified potential candidates for a potential password. However, before we can submit the potential password, we are presented with a small challenge. We recovered 1 password, however the system identified candidates from the list.. Let’s rerun the command and change the ```-w 3``` workload to 3 or high.
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%206%20-%20Hashcat/Hashcat0-17.png)

Ah, another clue!!! And I thought I would have to read the entire hashcat documentation and trial and error more commands. **All hashes found in potfile! Use --show to display them.** Let’s give this a try, ```hashcat --show -m 18200 password_list.txt```
The reason why we want to include ```-m 18200```, we want to load all hashes for ASREP for a response.
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%206%20-%20Hashcat/Hashcat0-18.png)

Upon further inspection, we can see lines 88 - 95 and 100-102 contains a **Salt-length exception**, while others contain a Separator unmatched response. We can narrow this list down by appending the command with ```| grep “exception”```
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%206%20-%20Hashcat/Hashcat0-19.png)

That helps narrow down our list from 144 options to 13. I asked ChatGPT the meaning behind the Salt-length exception.
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%206%20-%20Hashcat/Hashcat0-20.png)

The 13 passwords we cracked have different salt lengths. Upon further inspection with hashcat and exploring the internet on my last cup of hot chocolate for the evening, there is no solution for Kerberos for Salt-length exceptions. However, 13 is better than 144. I used the command ./bin/runtoanswer and typed in the potential password from the list of Salt-Exception passwords until I got a correct response.
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%206%20-%20Hashcat/Hashcat0-21.png)


### Additional Findings:
I am puzzled as to why I was unable to narrow down the password list from 13 potential passwords to 1 password. Based on the responses from ChatGPT and researching the internet, this is due to hashcat not supporting multiple salt lengths when cracking passwords. However, since I was able to use hashcat to identify the 13 potential passwords, if there were no restrictions on the user’s account that would lock the user’s account after 3 failed login attempts; this was a challenge we were able to accomplish.

In the real world, if the account was locked due to controls that are configured to lock accounts if there are at least 3 failed password attempts, there is an opportunity where the user is notified and would change their password, thus allowing a level of control as long as the user does not reuse old passwords.


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


## Chapter 8 Challenge: Luggage Lock
### Location: Island of Misfit Toys / Squarewheel Yard
There was an evening where my boyfriend was wondering why I was spending so much time after dinner on my computer focusing on completing the challenges and writing up my reports. He was curious on what each of the challenges entails and I found one that I challenged him to complete after I solved this one on my own.
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%208%20-%20Luggage%20Lock/LuggageLock1.png)

**Luggage Lock Decode** is a challenge that utilizes less hacking skills and is more informational and fun to perform. The youtube video provided by SANS https://www.youtube.com/watch?v=ycM1hBSEyog gives instructions on how to complete this challenge. This does require a bit of trial and error to complete the challenge. It was easy enough to figure out and challenged my boyfriend, who has no CTF experience, to have a go at luggage lock to see if he can figure it out. He did it in less time than I did [insert facepalm].

### How to complete the challenge:
1.  Start with one wheel and work your way up to four wheels.

2.  Apply pressure on the lock by using the spacebar. There are 5 modes of resistance that can be applied to the lock. We found resistance of 3-4 spacebar clicks.

3.  Use the [Q,A],[W,S],[E,D], or [R,F] keys to scroll up and down the wheel until you receive a response of resistance.

4.  Hit the spacebar until either of the two actions occur:
5.  The zipper opens and you complete the challenge.
6.  The zipper does not open, follow steps 2 - 4 until you open the zipper.

This is a quick and easy challenge we were able to achieve in less than 10 minutes to complete. I am curious if this will work with my match luggage that I have in the closet. For those who may be reading this, my combination is not 1,2,3,4,5.
https://github.com/akirylak/2023-SHH/blob/main/Chapter%208%20-%20Luggage%20Lock/LuggageLock2.png

## Chapter 9 Challenge: Na’an
### Location: Film Noir Island / Chiaroscuro City
Well, this is very different! An island that is in black and white and rainy. I feel very bad for the Goose of Film Noir Island, he looks very sad.
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%209%20-%20Naan/Chapter9-0.png)

Navigating the island, I came across a challenge titled Na’an. There are three things that come to mind when I see the word Naan.

1.  Naana Naana Naana Nanna Nanna Nanna Nanna Nanna….BATMAN!
2.  Nyan Cat
3.  Python

Opening up the challenge, I had a strong feeling I would be using Burp Suite again to complete this challenge. I highly recommend all users who are interested in CTF to learn to use Burp Suite.
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%209%20-%20Naan/Chapter9-1.png)

Playing the game as if I was not competing in a CTF challenge. I used the values 0,1,2,3,4 on each round to see if I could identify any randomization or patterns. What I did identify is there is consistency where no matter what numbers you choose, they will be the same response. After doing some exploring with finding a combination of numbers that would result in a tie, I came across the pattern 0,1,2,8,9.
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%209%20-%20Naan/Chapter9-2.png)

However, this is a game that is not about finding patterns. This is all about the term ```Nan```, (SANS holiday hack types it as Na’an). From experience, Nan stands for “Not a Number” and is used as a placeholder undefined values. Let’s ask ChatGPT what Nan is.
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%209%20-%20Naan/Chapter9-4.png)

Although Nan is a floating-point value, it supports decimal and non-decimal integers, it is not necessarily a number. (FYI, Integers in programming are whole numbers). We can leverage using Nan to replace numbers to give us a nan response. So, how do we do this if playing the game only allows us to input an integer. This is where we need to leverage BurpSuite.

We will follow the same instructions like we did to complete Reportinator. The only difference is we will not extract the URL link from the iframe and instead log into SANS Holiday Hack using the Chromium browser. Once we are at the point in the game where we input our number values, we will turn on the Interception button  in the Proxy tab.

Type in any non-repeating number values for the values of the cards. Click the play button and in Burp Suite use the forward button until we get to the screen where we are to our POST request.
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%209%20-%20Naan/Chapter9-5.png)

We can see in the ```{“play”: “4,3,2,10”}``` , we see our values that we are using the play the game. We can easily replace the numbers with the value of nan.
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%209%20-%20Naan/Chapter9-6.png)

Once we replaced all number values with nan, we will click Forward to forward our POST request.
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%209%20-%20Naan/Chapter9-7.png)

We can see not only we broke the game, we scored 2 points. We will repeat the process until we reach 10 total points.

### Additional Findings:
Alternatively, I discovered not all play values need to have Nan. We can complete the challenge by changing only one integer value to be Nan.
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%209%20-%20Naan/Chapter9-8.png)
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%209%20-%20Naan/Chapter9-9.png)


## Chapter 10 Challenge: Elf Hunt
### Location: Pixel Island / Rainraster Cliffs

![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%2010%20-%20Elf%20Hunt/Elfhunt1.png)
Upon completing this 100 page report, I wanted to jump to a favorite challenge of mine, Elf Hunt. I had something new to learn by using JSON (JWT) tokens to complete a CTF challenge. This was one I had clear cookies to complete twice to show my work on how I completed this challenge. For this challenge, I will leverage Burp Suite once again. I made sure that I installed the JWT Editor extension in Burp Suite to help complete this challenge.

We will also use a resource that is available by Port Swigger Academy to help us complete this challenge, https://portswigger.net/burp/documentation/desktop/testing-workflow/session-management/jwts
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%2010%20-%20Elf%20Hunt/Elfhunt2.png)

Once we identify the HTTP page that is for Elf Hunt (JWT extension will highlight the requests in green), we will right click the request and send to Repeater.

In the repeater tab, in the request we can identify the Cookie for ElfHunt_JWT. We will next click on the JSON Web Token tab to modify the JSON web token.
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%2010%20-%20Elf%20Hunt/Elfhunt3.png)

Inside the JSON Web Token tab, we can identify the payload of  ```{“speed”: -500}``` that is attached to the JWT token.
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%2010%20-%20Elf%20Hunt/Elfhunt4.png)

We can modify the Payload by changing the value of -500 to -100. I would not recommend 0 as when testing, 0 did not allow any elves to come out in the game. If -100 is too fast, we can alternatively lower the number to -75.
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%2010%20-%20Elf%20Hunt/Elfhunt6.png)

At the bottom of the JSON Web Token tab, we will click the Sign button to sign our token. If this option is not available in your version of Burp Suite, follow the video below on how to create a private key: https://portswigger.net/burp/documentation/desktop/testing-workflow/session-management/jwts
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%2010%20-%20Elf%20Hunt/Elfhunt5.png)

Once you sign your key, copy and paste the new JSON web token.
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%2010%20-%20Elf%20Hunt/Elfhunt7.png)
Inside the Chromium browser, right click the iframe and click Inspect. This can also be performed using Google Chrome browser.
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%2010%20-%20Elf%20Hunt/Elfhunt8.png)

Inside the developer tools click on the Application tab and on the left hand side navigation menu, click on the Cookies dropdown under storage. Locate the cookie for elfhunt.org.
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%2010%20-%20Elf%20Hunt/Elfhunt9.png)

Modifying the cookie is as easy as right-clicking the value of the cookie, and clicking Edit “Value”.
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%2010%20-%20Elf%20Hunt/Elfhunt10.png)

Paste the new value of the cookie to replace the old value of the cookie.
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%2010%20-%20Elf%20Hunt/Elfhunt11.png)

Now the next step is critical. Refresh the browser window to reload the game. The modified JWT token for the cookie will load into the Elf Hunt game and you will notice the speed of the elfs will be drastically reduced. Complete the game as if you were to play the game until you reach 75 points.
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%2010%20-%20Elf%20Hunt/Elfhunt12.png)

After solving Elf Hunt, a little surprise is revealed to you by clicking on the Game Token.

## Final Words
I am very impressed by the SANS team and those who collaborated on this project for 2023. As much as I wanted to participate in the 2022 Holiday Hack; at the time I did not have the skills that I have today to complete the challenges, nor did I have any knowledge about Burp Suite, which was an extremely valuable tool for this year.

In regards to using ChatGPT to help solve some of the challenges, it was a learning curve using the tool as there are limitations on what the tool can and cannot do. A perfect example is phrasing your requests to allow the AI engine to give you a response.

Example: “How to escalate privileges in Linux?”
![](https://github.com/akirylak/2023-SHH/blob/main/Final%20Words/finalwords1.png)

There were many times during the Hashcat, LinuxPrivEsc and Linux 101 where I had to ask questions in the form of “ what is” rather than “how to”.

As much as I wanted to complete all of the challenges and write a full report of every chapter, time has run out and I am running out of pages to type a full report for the submission for the Holiday Hack. If the Holiday hack is still available for users to play with after the fact, I would love to make an attempt and write a full report. I would also love to solve the challenge for “Snowball Fight” as I got lucky with solving the challenge by completing the game.

My favorite challenges for this year’s 2023 Holiday Hack are:
LinuxPrivEsc
Hashcat
Elf Hunt
Reportinator


# Honorable Mentions

## Challenge: Faster Lock Combination
This was a challenge where ChatGPT was not needed to be used as there are resources available online on how to solve the challenge.

SANS Holiday Hack recommended this youtube video to watch.
https://www.youtube.com/watch?v=27rE5ZvWLU0
This was a tool I discovered using Google Search
https://samy.pl/master/master.html

## Challenge: Game Cartridges: Vol 1
This was a breath of fresh air where simply exploring the game and solving the problem to fix the QR code. This game required more strategy and identifying the pattern and resetting the QR code if you got stuck.

## Challenge: Bonus! Fishing Guide
I am curious to know who did the artwork for the fish that surround the Geese Islands as the artist should consider creating a “Go Fish” or “Go Phish” game out of these cards. Artwork was fantastic and the game was a great excuse to explore the islands to find more challenges.
