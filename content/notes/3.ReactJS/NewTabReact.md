---
title: "NewTabReact"
tags:
- react
- projects
- how-to
- step-by-step
---

I've seen some really cool NewTab front pages for featured on github for [r/unixporn](https://www.reddit.com/r/unixporn/)
LIKE
- [Bento](https://github.com/migueravila/Bento)
- [markdown--new-tab](https://github.com/plibither8/markdown-new-tab)
- [devo](https://github.com/karakanb/devo)
- [mue](https://github.com/mue/mue)

## The Design

![Safari • Dark Mode ON 1](notes/3.ReactJS/attachments/Safari_dark_mode.png)


## Simple Features
- AutoScrapped Quotes
- Weather
- Chess Puzzle from lichess API

### Component BreakDown
![](notes/3.ReactJS/attachments/NewTabReact%202023-07-01%2001.26.09.excalidraw.svg)
%%[🖋 Edit in Excalidraw](notes/3.ReactJS/attachments/NewTabReact%202023-07-01%2001.26.09.excalidraw.md), and the [dark exported image](notes/3.ReactJS/attachments/NewTabReact%202023-07-01%2001.26.09.excalidraw.dark.svg.md)%%

## Make the Basic Structure of the App

## NavBar
This one is actually oddly simple, as the basic structure of the navbar is only based on GoogleSearch being hooked too the input, some border style and we are done

```js
import './Navbar.css'

function Navbar() {
  return (
  <div className='nav_container'>
     <nav className='nav_bar'> <input className="search_bar" type="?" placeholder=' Google Search '/>  </nav> 
  </div>
  );
}

export default Navbar;
```

CSS
```css
.nav_container {
    display: flex;
    justify-content: center;
    margin: 30px 0 30px 0;
}

.search_bar{
    border: 3px solid cyan;
    width: 300px;
    height: 30px;
    border-radius: 20px;
    text-align: center;
    font-size: large;
    background-image: url("searchIcon.svg");
    background-repeat: no-repeat;
    background-size: contain;
    background-position: right;

}
```

![](notes/3.ReactJS/attachments/Peek%202023-07-27%2018-24.gif)


## Input entry to Google search
Simple HTML was just applied !
```html
 <form action="http://www.google.com/search" method="get">
	<input className="search_bar" name="q" type="text" placeholder=' Google Search '/>
</form>
```

## The Action Attribute

The `action` attribute defines the action to be performed when the form is submitted.

Usually, the form data is sent to a file on the server when the user clicks on the submit button.

In the example below, the form data is sent to a file called "action_page.php". This file contains a server-side script that handles the form data:

**Notes on GET:**

- Appends the form data to the URL, in name/value pairs
- NEVER use GET to send sensitive data! (the submitted form data is visible in the URL!)
- The length of a URL is limited (2048 characters)
- Useful for form submissions where a user wants to bookmark the result
- GET is good for non-secure data, like query strings in Google

**Notes on POST:**

- Appends the form data inside the body of the HTTP request (the submitted form data is not shown in the URL)
- POST has no size limitations, and can be used to send large amounts of data.
- Form submissions with POST cannot be bookmarked

### Logic of Za URL forms (Google)
![](notes/3.ReactJS/attachments/NewTabReact%202023-07-27%2018.36.48.excalidraw.svg)
%%[🖋 Edit in Excalidraw](notes/3.ReactJS/attachments/NewTabReact%202023-07-27%2018.36.48.excalidraw.md), and the [dark exported image](notes/ReactJS/attachments/NewTabReact%202023-07-27%2018.36.48.excalidraw.dark.svg)%%

- [ ] Make the search icon an object instead of background #task 

## Making a theme generated background paper
Not possible ?
Found [BGJar](https://bgjar.com/) to for really nice background patterns!

# Implementing a Working clock

## An Updating Clock and "useEffect" - ChatGPT

To implement an updating clock in React, you can follow these steps:
1. Create a new React component for the clock. For example, you can name it "Clock".
2. In the component, initialize a state variable to hold the current time. This can be done using the `useState` hook.
```jsx
   import React, { useState } from "react";

   const Clock = () => {
     const [time, setTime] = useState(new Date());

     return (
       <div>{time.toLocaleString()}</div>
     );
   };

   export default Clock;
```

3. Next, you need to update the time every second. This can be achieved using the `setInterval` function. At the same time, you should handle the cleanup of the interval when the component unmounts. To do this, you can use the `useEffect` hook.

   ```jsx
   import React, { useState, useEffect } from "react";

   const Clock = () => {
     const [time, setTime] = useState(new Date());

     useEffect(() => {
       const timerID = setInterval(() => setTime(new Date()), 1000);
       return () => {
         clearInterval(timerID);
       };
     }, []);

     return (
       <div>{time.toLocaleString()}</div>
     );
   };

   export default Clock;
```

4. Finally, you can render the `Clock` component in your main app component or any other component where you want to display the clock.


```jsx
   import React from "react";
   import Clock from "./Clock";

   const App = () => {
     return (
       <div>
         <h1>Current Time:</h1>
         <Clock />
       </div>
     );
   };

   export default App;
```

With these steps, the clock component will update the displayed time every second while using React's state and hooks.

### The [[notes/3.ReactJS/Fundamentals/useEffect|useEffect]]
The `useEffect` hook is a built-in hook in React that allows you to perform side effects in functional components. Side effects are any code that needs to be executed outside the normal flow of the component, such as fetching data, subscribing to events, or manually modifying the DOM.

The `useEffect` hook takes two parameters: a callback function and an optional dependency array. The callback function is executed after the component renders, and it can return a cleanup function that will be executed before the component is unmounted or re-rendered. The dependency array specifies the values that the effect depends on, and it allows you to control when the effect should run or be skipped.

Here's an example of using `useEffect` to fetch data from an API:

```javascript
import React, { useEffect, useState } from "react";

function MyComponent() {
  const [data, setData] = useState([]);

  useEffect(() => {
    // Fetch data from API
    fetch("https://api.example.com/data")
      .then((response) => response.json())
      .then((data) => setData(data));
  }, []);

  return (
    <div>
      {data.map((item) => (
        <p key={item.id}>{item.name}</p>
      ))}
    </div>
  );
}
```

In this example, the effect will run only once, immediately after the component renders for the first time, because the dependency array is empty. If you specify a dependency array with values, the effect will run whenever any of those values change.

[[notes/3.ReactJS/Fundamentals/useEffect|useEffect]] is a powerful tool for managing side effects in functional components and helps to keep the logic of the component organized and easy to understand.

- [ ] Hook QOTD and Weather API to [[notes/3.ReactJS/NewTabReact|NewTabReact]] #task