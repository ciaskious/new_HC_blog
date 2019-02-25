---
title: "SkillSpace || Week 3 --> A full week of JavaScript"
date: 2019-02-25T16:44:44+01:00
draft: false
tags: ["masterpiece", "javascript"]
---

It would take me a whole day to go back to a week's code and document my learnings into this post. Suddenly though, it makes so much sense to write blog posts to document our learnings real-time . Posts that can write themselves and help us solve each other's issues. It happened multiple times during the previous week, that we bumped into issues that we had solved already. So from now on, the editor will be always open waiting for us to blog tweet sized posts.  

Tomorrow we will deploy the new features of SkillSpace. Not perfectly made, but they serve the core purpose of this project. Tomorrow users will be able to share their skills on their profiles and be found by others in the platform either by name or skill. It took me a lot of time to become familiar with the stack: playing with material ui components, creating my own components in react and in the end combining everything to create a nice searching experience; sounds poetic but proved to be be extremely painful.  

It seems that React could not work for us with searching very smoothly. Although the logic was created, it had to go through the server to work with the Searchbar in the frontend. Our idea was to create a nice dropdown _onChange()_, already in categories (users, skils, location, etc), in order to give instant results to the user and create a nice experience. Instead of this, an _onRequest()_ event captures the state of the bar and sends the value to the server, where our searching functions are called and the results are passed again to the frontend, to our results' components. I found it a good practice for props, I can now finally pass props to my components without much thinking.  
### Tip: `Event handlers as props`.  
 Instead of binding the function in render, use arrow syntax to define the function. This way, you don't create the new function every time the component is being rendered. Eg.  

```
//define with arrow syntax
handleSearch = (value) => {
        window.location.href = '/your-results-url/' + value;
    }

    render(){
      <componentA>
        // blah
        <componentB>
          //blah blah
          onRequestSearch={() => this.handleSearch(this.state.value)}
        </componentB>
      </componentA>

    }
```

There must be a better way for this process, we have a solution that works but might become slower when searching grows in dimensions.

[Song of the day](https://www.youtube.com/watch?v=nAEz6tn-O4A)
