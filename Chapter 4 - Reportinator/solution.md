#SANS Holiday Hack 2023: SimonCypherSays Report
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
