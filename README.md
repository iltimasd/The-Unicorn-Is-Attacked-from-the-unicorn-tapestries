# [The Unicorn is Attacked (from the Unicorn Tapestries)][1]
## A clunky hack to add peeps to Unicornucopia

![*The Unicorn is Attacked (from the Unicorn Tapestries)*. 1495–1505. Wool warp with wool, silk, silver, and gilt wefts. The Metropolitan Museum of Art, New York.](https://images.metmuseum.org/CRDImages/cl/web-large/DP118985.jpg)

# FULL DISCLOSURE: It's super hack-y, and not really sure how the backend handles badly formated requests, I've already created ideas that have no owners, idk how bad you could mess it up, but hey, what doesnt kill you...

How this hack works: Unicornucopia(Uni from here on out) already uses API calls to submit ideas. All this hack does is intercept XMLHttpRequest and then edit and resend via Postman Console and Postman interceptor. 


1. Install the tools. Postman Intercept(plugin). Postman Console.

[Postman Console Link][2]
[Postman Chrome Plugin][3]

2. Toggle console to except intercepted XHR content

0. Open Uni

![toggleconsole](https://www.getpostman.com/img/v1/docs/interceptor_cookies/interceptor_cookies_1.png)

3. Toggle plugin to start intercepting(ideally close all your other tabs)

![toggleplugin](https://s3.amazonaws.com/postman-static-getpostman-com/postman-docs/proxy.interceptExt.png)

You're gonna want to close your other Chrome tabs. Sites like Facebook or Twitter 
is often making requests, so you might get a lot of noise from these sites.

4. Submit idea on site to capture XHR content

This is where we'll actually trigger a request in order to capture it. Specifically 
we want your tokens and we
want the JSON format that we can easily edit

5. Pull up POST request on console and navigate to Body tab

From the side panel select the POST request you just captured. Click on the "Body" tab. 
*the "Header" tab is where your token lives. Uni seems to not use regular headers for Auth, 
which you can see in the Authorization tab. Check it out*

6. Edit author numbers

If you thought it was friction-y now...

So now we actually need the numbers associated with an account.
I believe the easiest way is to search and select the user in the sidebar and the author 
number will appear a query paramater.

7. Edit body content

Now edit the body. This is your idea

8. Send!

Hit Send!

You can now change the body content without having to input team members.

Also you can only add 40 authors, so adding the whole class is hard. 
Theoretically you coordinate sections. and everyrone in the 40 person section submits 3
ideas and then boom, you got 120 ideas attributed to you. It takes some coordination. OR
you could just continually add the people on your bi-weekly group. in theory, if each team does 10 ideas a week, week 1 is 10 ideas, week 2 is 50 more ideas, and week 3 is more than 50 ideas, boo yah A+

[1]:https://www.metmuseum.org/art/collection/search/467639
[2]:https://www.getpostman.com/apps
[3]:https://chrome.google.com/webstore/detail/postman/fhbjgbiflinjbdggehcddcbncdddomop?hl=en
