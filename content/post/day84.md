---
title: "Day86: SkillSpace || Week2 -> Surviving the frontend"
date: 2019-02-14T16:23:42+01:00
draft: false
tags: ["javascript", "masterpiece"]
---

If you ask me what I don't enjoy the most in this life, I would say okra and fixing the frontend. For the first, I was making sure there is an alternative home when mom made okra ( now I just don't cook it). For the second... I decided that I have to deal with it!  

### `Users can login, but logout screws up the css.`  

After finishing part of the authentication, we continued with our user story. `As a user I am able to login in the platform and view my profile`. You can view your own and your peers' profiles. So, on the backend side things were pretty easy and straightforward, but on the frontend pretty ugly. For both of us, css causes stress. And this is when Material Design came in the game. In fact, a react framework that implements MD in components. Couldn't get easier, the components (beautiful I must say, as MD comes from Google) are a copy-paste away. Components that I have heard a lot about, but haven't used that extensively. This time, it was not just a couple of buttons, but whole parts of the pages that work independently: skills, recognitions, info section and a lot more. It was easy to give structure with this framework, especially today that we gave life and color to every part of the frontend. Yesterday, when the login form was created we played around a little bit and found an issue: users log in filling out a beautiful form, but when they log out they get redirected to a form of pure html. I could fill one whole page with how much we struggled to end up to the right google result...

#### What was wrong
Well there is very good documentation on Material UI, we just decided to pay the price for not reading through it. There is a very clear, well-written section about _server-side rendering_ (our case), which we missed:  
`When the server receives the request, it renders the required component(s) into an HTML string, and then sends it as a response to the client. From that point on, the client takes over rendering duties.`

> Material-UI was designed from the ground-up with the constraint of rendering on the Server, but it's up to you to make sure it's correctly integrated. It's important to provide the page with the required CSS, otherwise the page will render with just the HTML then wait for the CSS to be injected by the client, causing it to flicker.

Once we understood the above, the rest was copy paste. **With every request**, you create new _sheets registry_ and _theme_ instances on the server. After they are rendered with react, the css can be pulled and passed to the client. Then, it worked!!!

#### Was it wrong to consider adopters with the first feature?  

Seems like it. Having adopters, without delivering value doesn't make much sense. A login and a profile without functionality, don't bring much value to user to the user; it was just our way to kick-off the project. It was the wrong approach for a team that wants to be lean, but maybe right for the team that is still uncomfortable with the tech stack. :) All mistakes are learnings and all learnings are welcome!!  

[Material UI Documentation: Server Side rendering](https://material-ui.com/guides/server-rendering/#server-rendering)  

[Song of the day](https://www.youtube.com/watch?v=nYYj15htuKI)
