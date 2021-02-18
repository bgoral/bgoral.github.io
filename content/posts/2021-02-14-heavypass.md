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

I also think the future of authentication will be password-less [link][1]. Although we are very close to this future, we are not there yet. Still, more or less all of the applications require some sort of password, but enhancing passwords with some additional validation ([Multi Factor Authentication][2]) like SMS, Authenticator Apps, Biometric scanning etc. In addition to that, we are being forced to change passwords after some time and most of the time not allowed to use one of the last 3 passwords. These practices are required because there are people continuously trying to hack your accounts, why? I think this will take us to a philosophical discussion about hackers and hacking. I prefer to be as described in [Hackers and Painters][3]. Under these circumstances; we, humble human beings continue to forget passwords and tending to use crackable, memorable and short passwords. I built [HeavyPass][4] to generate memorable and strong (+ \Heavy/) passwords.

The idea behind [HeavyPass][4] is based on [Passphrase][5]. 
> Passphrases are theoretically stronger, and so should make a better choice in these cases. First, they usually are (and always should be) much longer —20 to 30 characters or more is typical— making some kinds of brute force attacks entirely impractical. 


### Why HeavyPass?

If you are a Heavy Metal fan, remember songs and lyrics and can play songs with your [air guitar][6]. [HeavyPass][4] is an application for you. 


### The tech stack

- Backend : ASP .Net Core 
- Frontend : React + Semantic UI, [Unsplash][8]
- Database : Mongo DB - Atlas
- Data Collecting : Nodejs, cherryio
- Platform : Heroku

### Challenges and highlights

- Asynchronous programming brings an overhead on debugging and once needs to focus a lot on concurrency and parallelism. This was my first challenge when trying to extract heavy metal albums from the web. "Promise" concept helped a lot but also lack of security in web sites and IP rate filtering. 

- When you have roots in pure CSS and JavaScript, the learning curve of ReactJS is lesser but still unable to understand the requirement for this complex build and debug toolchain. Even after I removed all unrequired references, my "node_modules" folder is around 250MB. I hope some Nodejs enthusiasts are as of now building solutions for this. Nodejs is not green at all and I will measure the amount of energy spent during the project build and debugging and deployment later. 

- [Unsplash][8] by beautifully opening their random image [API][9].

- I was not planning to use MongoDB. In the beginning, I started with PostgreSQL (because I am a Fanboy). I was planning to use Azure App services and PaaS PostgreSQL. When I see the cost statistics, I decided to move to more developer-friendly options. For such a frontend scenario, MongoDB is one of the best options and Atlas is providing a great free startup option. I had 0 issues. 

- [Heroku][10] is a superior platform if you are a developer just want to experiment with your ideas in a battle-tested environment in a technology you like with low cost or no cost. I started with the developer account completed the application, deployed without any issue. I did have 0 issues. But If you want to run .Net, the platform requires familiarity with Docker builds.


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