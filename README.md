# [The Unicorn is Attacked (from the Unicorn Tapestries)][1]
## A clunky hack to add peeps to Unicornucopia

![*The Unicorn is Attacked (from the Unicorn Tapestries)*. 1495–1505. Wool warp with wool, silk, silver, and gilt wefts. The Metropolitan Museum of Art, New York.](https://images.metmuseum.org/CRDImages/cl/web-large/DP118985.jpg "*The Unicorn is Attacked (from the Unicorn Tapestries)*. 1495–1505. Wool warp with wool, silk, silver, and gilt wefts. The Metropolitan Museum of Art, New York.")

## Table of Contents
- [Land Narwhal](#a-clunky-hack-to-add-peeps-to-unicornucopia)
- [This](#table-of-contents)
- [Why?](#why)
- [DISCLOSURE](#full-disclosure-its-super-hack-y-and-not-really-sure-how-the-backend-handles-badly-formated-requests-ive-already-created-ideas-that-have-no-owners-idk-how-bad-you-could-mess-it-up-but-hey-what-doesnt-kill-you)
- [The Actual Thing](#how-to)
- [What I Actually Want The Acutual Thing to Actually be, Actually](#next-steps)
- [FAQ](#faq)

## Why?

First and foremost, this is step in a direction to minimize a friction I see in a product. Now usually when a friction occurs, for example when I'm forced to do a 5-minute onboarding for pinterest, I'll usually just drop the service. Unfortunatley, there are some services out there where this isnt a solution, whether it's seeing hate speech on platform(twitter) that also aided in a people's movement to take back the goverment OR having to do repetitive tasks to accomplish one action on a platform(uni) that I'm required to use. In these cases, I try to seek interventions I can from a civilian level. Second, as a design technologist, I'm interested both in seeing what make platforms tick, and what makes platforms tick that make users tick. So this is also a sort of investigation in that. Additionally, as a student of design AND technology, I'm interested in what it means to use technology, in this case a social media platform, in the effort to learn technology; I'm interested in interagating what it means when we use systems, like gamification, in pedagogy, and what that does to the learning experience. I hope these ideas interest you too <3 

## FULL DISCLOSURE: It's super hack-y, and not really sure how the backend handles badly formated requests, I've already created ideas that have no owners, idk how bad you could mess it up, but hey, what doesnt kill you...

## How to

### 0. Install the tools. Postman Intercept(plugin). Postman Console.

[Postman Console Link][2]

[Postman Chrome Plugin][3]

### 1. Open Uni

### 2. Toggle console to except intercepted XHR content

![toggleconsole](https://www.getpostman.com/img/v1/docs/interceptor_cookies/interceptor_cookies_1.png)

### 3. Toggle plugin to start intercepting(ideally close all your other tabs)

![toggleplugin](https://s3.amazonaws.com/postman-static-getpostman-com/postman-docs/proxy.interceptExt.png)

You're gonna want to close your other Chrome tabs. Sites like Facebook or Twitter 
is often making requests, so you might get a lot of noise from these sites.

### 4. Submit idea on site to capture XHR content

This is where we'll actually trigger a request in order to capture it. Specifically 
we want your tokens and we
want the JSON format that we can easily edit

### 5. Pull up POST request on console and navigate to Body tab

From the side panel select the POST request you just captured. Click on the "Body" tab. 
*the "Header" tab is where your token lives. Uni seems to not use regular headers for Auth, 
which you can see in the Authorization tab. Check it out*

![Pull up POST request on console and navigate to Body tab](https://raw.githubusercontent.com/iltimasd/The-Unicorn-Is-Attacked-from-the-unicorn-tapestries/master/capture1.PNG "Pull up POST request on console and navigate to Body tab")

### 6. Find author id numbers

*If you thought it was friction-y now...*

So now we actually need the id numbers associated with an account.
I believe the easiest way is to search and select the user in the sidebar and the author 
number will appear a query paramater.

![Edit author numbers](https://raw.githubusercontent.com/iltimasd/The-Unicorn-Is-Attacked-from-the-unicorn-tapestries/master/capture2.PNG "Edit author numbers")

### 7. Edit author and body content

Add the id numbers to author field, edit the body with your idea.
### 8. Send!

Hit Send!

You can now change the body content without having to input team members everytime!

Also you can only add 40 authors, so adding the whole class is hard. 
Theoretically you coordinate sections. and everyrone in the 40 person section submits 3
ideas and then boom, you got 120 ideas attributed to you. It takes some coordination. OR
you could just continually add the people on your bi-weekly group. in theory, if each team does 10 ideas a week, week 1 is 10 ideas, week 2 is 50 more ideas, and week 3 is more than 50 ideas, boo yah A+

### 9. Save!
You can save this so now you just change author numbers(or add author number ;)) so you dont have to redo steps 0-4.

[1]:https://www.metmuseum.org/art/collection/search/467639
[2]:https://www.getpostman.com/apps
[3]:https://chrome.google.com/webstore/detail/postman/fhbjgbiflinjbdggehcddcbncdddomop?hl=en

## Next Steps

Ok here's we could really nail it! So Postman has this CLI interface called Newman. Postman also accepts external JSONs and can use variables to programatically send requests. With that known, I'm thinking we could make a way to have a CLI interface for this.

```bash
$ echo " "authors":"[51,23,45,159]" " >> authorIDnumbers.json

$ newman run theUniRequest.json --global-var "<body>=<"CLI commands that can easily add collaborators to a project idea on uni">" -d authorIDnumbers.json

```

^Obviously psuedo-code-y, but you get the idea. And I'm even sure this could be like even less friction-y! Maybe there could as easier way to do this.

# FAQ

- Why are you doing this?

	Maybe read [this](#why)

- Why are you making this public?

	It's imperative to share code in technology-education spaces. The diffence between the academic industrial complex and education is in sharing of resources, tools, and findings, no matter if your the Dean or a first year student, or anyone inbetween and outside.

- Is this a pathetic stab to be a white-hatter and get invited to present at DEFCON?

	Savage . . . but yes.

- Don't you have better things to do?

	absolutely. This is what we call procrastination. What I should be working on is my Parsons Studio Final where I'm working on a blogging platform for Work-in-Progress documentation that uses texting as a low-friction submission mechanic both for personal use and as an archiving tool for college programs/departments, and my Cornell-Tech Product Studio Final where my team is building a platform that combats hate speech on twitter by connecting users with experts that provide talking point to inject into hate content. 

- This is, like, not even a good fix for this problem?

	I agree. Come help: Look at Next Steps and make a pull request. Have copy edits for this readme: make a pull request. Think there should be other Next Steps: make it an issue.
