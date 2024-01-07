# SANS HOLIDAY HACK 2023: SimonCypherSays Report
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
