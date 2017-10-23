# [The Unicorn is Attacked (from the Unicorn Tapestries)][1]
## A clunky hack to add peeps to Unicornucopia

![*The Unicorn is Attacked (from the Unicorn Tapestries)*. 1495–1505. Wool warp with wool, silk, silver, and gilt wefts. The Metropolitan Museum of Art, New York.](https://images.metmuseum.org/CRDImages/cl/web-large/DP118985.jpg)

How this hack works: Unicornucopia(Uni from here on out) already uses API calls to submit ideas. All this hack does is intercept XMLHttpRequest and then edit and resend via Postman Console and Postman interceptor. 
# FULL DISCLOSURE: It's super hack-y, and not really sure how the backend handles badly formated requests, I've already created ideas that have no owners, idk how bad you could mess it up, but hey, what doesnt kill you...

1. Install the tools. Postman Intercept(plugin). Postman Console.
2. Toggle console to except intercepted XHR content
3. Toggle plugin to start intercepting(ideally close all your other tabs)
4. Submit idea on site to capture XHR content
5. Pull up POST request on console
6. Edit author numbers
7. Edit body content
8. Send!



[1]:https://www.metmuseum.org/art/collection/search/467639
