---
title: "Heaviest Password Generator"
date: 2021-02-15T12:07:19+01:00
draft: false
categories: 
- Life
tags:
- Project
---

## HeavyPass

I  think the future of authentication will be [passwordless][1]. We are very close to that future but not there yet. Still, most of the applications require username and passwords, but enhancing with additional validation methods ([Multi Factor Authentication][2]) like SMS, Authenticator Apps, Biometric scanning etc. In addition to that, users are being forced to change their passwords after some time and mostly not allowed to use one of the last 3 passwords. Under these circumstances; we, humble human beings continue to forget passwords and tending to use memorable, short and , crackable passwords. I built [HeavyPass][4] to generate memorable and strong (+ \Heavy/) passwords.

The idea behind [HeavyPass][4] is [Passphrases][5]. 

> Passphrases are theoretically stronger, and so should make a better choice in these cases. First, they usually are (and always should be) much longer —20 to 30 characters or more is typical— making some kinds of brute force attacks entirely impractical. 


### Why HeavyPass?

If you like Heavy Metal music, remember songs and lyrics [HeavyPass][4] specifically for you. 


### The tech stack

- Backend : ASP .Net Core 
- Frontend : React + Semantic UI, [Unsplash][8]
- Database : Mongo DB - Atlas
- Data Collecting : Nodejs, cherryio
- Platform : Heroku

### Challenges and highlights

- Asynchronous programming brings an overhead on debugging and beware of concurrency and parallelism. "Promises" helped a lot but also lack of security and IP rate filtering. 

- When you have roots in pure CSS and JavaScript, learning ReactJS is relatively easy but I think build and debug toolchain is over complex. Even after I removed all unrequired references, my "node_modules" folder is appx. 250MB. Sorry but Nodejs is not green at all, wasting lots of unnecessary power. 

- Thanks to [Unsplash][8] by beautifully opening their random image [API][9].

- I was not planning to use MongoDB. I started with PostgreSQL (because I am a Fanboy). I tried to use Azure App services and PaaS PostgreSQL. After I see unexpected cost data, I decided to move to more hobbyist options. For such a frontend scenario, MongoDB is one of the best options and Atlas is providing a great free startup option. I had 0 issues. 

- [Heroku][10] is a superior platform if you are a developer and just want to experiment on your ideas in a battle-tested environment in a technology you like with low cost or no cost. I started with the developer account completed the application, deployed without any issue. If you want to run .Net, the platform requires familiarity with Docker builds.


### Todo's

- Publish the codes of frontend, 
- After enhancing the security, publish the full codebase
- Copy when clicking each password
- More user-friendly UI
- Offline Mobile Application


### ***\Long Live Heavy Metal/***




[1]: https://www.darkreading.com/endpoint/why-the-future-is-passwordless/d/d-id/1339530 "Future is Passwrodlesss"
[2]: https://en.wikipedia.org/wiki/Multi-factor_authentication "Multi-Factor Authentication"
[3]: https://www.goodreads.com/book/show/41793.Hackers_Painters "Hackers and Painters"
[4]: https://www.heavypass.com "HeavyPass"
[5]: https://en.wikipedia.org/wiki/Passphrase "Passphrase"
[6]: https://www.merriam-webster.com/dictionary/air%20guitar "Air Guitar"
[7]: https://en.wikipedia.org/wiki/Metallica_(album) "Metallica"
[8]: https://unsplash.com/ "Unsplash"
[9]: https://source.unsplash.com/ "Unsplash Random API"
[10]: https://heroku.com "Heroku"