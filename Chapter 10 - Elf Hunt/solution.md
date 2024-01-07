# SANS HOLIDAY HACK 2023: SimonCypherSays Report
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
