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
