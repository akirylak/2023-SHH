# SANS HOLIDAY HACK 2023: SimonCypherSays Report
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
