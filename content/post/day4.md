---
title: "Day4: Intro to vim"
date: 2018-10-05
tags: ["vim", "markdown"]
draft: false
---
### Mark this down.

So, today' s _Friday_. 😎 It is the end of a new beginning and time to get my hands dirty. My previous posts were too plain, so I decided it is time to learn markdown. I admire all these pretty, colored and structured readmes, but I never cared about mine. Therefore, I devoted one hour  following a tutorial on the basics and here I am writing finally a descent post. My eyes thank me already...  
I have the link of the tutorial at the end of the post :)  

As I am trying to organize myself, I will experiment with learning in __one-week sprints__.  

> In such short sprints I can set short term goals, move faster and have more control of my backlog. I stay focused and avoid getting stuck into endless reading/googling loops.    

Speaking of backlog, one of the things I love using but I wasn't sure why is the _vim editor_. I edited my first file with vim last year; it was a hot summer evening during a docker workshop... the guy next to me was experienced and at some point proposed: "type vim foo.txt!"... **BOOM**!  
Of course it was impossible to exit ( [more on this tradedy](https://stackoverflow.blog/2017/05/23/stack-overflow-helping-one-million-developers-exit-vim/) ), but he saved me right away. Since then, I have been using only vim and laughing on the inside when people didn't know. But I knew... "ESC + :wq". Unfortunately for months this was the only reason I was using it. But the more stupid I feel sometimes, the more I learn in the end.  
So my goal is to explore both vim and emacs, draw my own conclusions and decide what suits me the most. Today I am introducing myself again to vim.

### **What is vim?**

![vim: just kidding](https://media.giphy.com/media/l4FAYXXoAJTUcZ0oo/giphy.gif)  
[via GIPHY](https://gph.is/2tAPftV)

Vim is an **editor**. If the terminal is your friend, once you learn how to exit vim, you will love it. Why?

* It makes you productive.  
If you have been using notepads for every single edit in your files, it will change your life. You save so many seconds (in the end minutes?) using your keyboard (only!) for minor changes.  
* It is super configurable.  
There are so many options for your .vimrc file.  
Just one note for Mac users: **Do not override your vimrc in your /usr dir.**  
Instead, create a new .vimrc file in your root directory and do all the customizations you want.

For example, this is all I need on my editor for now:

```vim
1 set nu                          "Show editor lines"
2 set autoindent                  "Auto-identation of a line"
3 set spell spelllang=en_us       "Spell-check for en"
4 set autoread                    "Reload files changed outside vim"
5 set wrap                        "Wrap lines"
6 set linebreak                   "Wrap lines at convenient points"
~     
~                          
~   
```


If you already have an idea of vim and you just want to get to know each other better, just type:

```vim
$ vimtutor
```
and enjoy the tutorial.

People get 🤢 by vim but it is just a matter of time until you practice enough and unlock its powerfulness. 🧞‍ It's worth a try! 😉

I will come back next week with cooler vim tips, but it will be mostly Scala week.

🌈Have a great weekend!  

[The vim book](ftp://ftp.vim.org/pub/vim/doc/book/vimbook-OPL.pdf)

[Markdown Tutorial](https://www.markdowntutorial.com)

#### [🎶 of the day](https://www.youtube.com/watch?v=aH_UesUJsm8)
