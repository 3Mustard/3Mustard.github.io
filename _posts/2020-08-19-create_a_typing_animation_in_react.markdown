---
layout: post
title:      "Create a 'typing...' animation in React"
date:       2020-08-19 11:29:44 -0400
permalink:  create_a_typing_animation_in_react
---

![](https://media.tenor.com/images/3b36f7623200da438dd4d35181659398/tenor.gif)

Today I am going to show you how to create an animation to show that a user is typing. If you have used chat rooms like Slack or Discord you may have noticed this effect. 

First let's assume we have a chat box component that is listening and updating a value in state to indicate if a user is typing or not.

```
class ChatBox extends React.Component {
    state = {
        isTyping: false
    }

    render() {
        <div><div>
    }
}
```


Next lets make the typing animation component. Essentially this will be a div with 3 divs in it. Some css tricks will turn it into a rectangle with 3 dots in it though.

```
const Typing = () => (
  <div className="typing">
    <div className="typing__dot"></div>
    <div className="typing__dot"></div>
    <div className="typing__dot"></div>
  </div>
)
```

Now some css to style and animate our three divs.


```
.typing {
  width: 5em;
  height: 2em;
  position: relative;
  padding: 10px;
  margin-left: 5px;
  background: #e6e6e6;
  border-radius: 20px;
}

.typing__dot {
  float: left;
  width: 8px;
  height: 8px;
  margin: 0 4px;
  background: #8d8c91;
  border-radius: 50%;
  opacity: 0;
  animation: loadingFade 1s infinite;
}

.typing__dot:nth-child(1) {
  animation-delay: 0s;
}

.typing__dot:nth-child(2) {
  animation-delay: 0.2s;
}

.typing__dot:nth-child(3) {
  animation-delay: 0.4s;
}

@keyframes loadingFade {
  0% {
    opacity: 0;
  }
  50% {
    opacity: 0.8;
  }
  100% {
    opacity: 0;
  }
}
```


Last step is to add our animation in to our ChatBox when this.state.isTyping is true.


```
class ChatBox extends React.Component {
    state = {
        isTyping: false
    }

    render() {
		  const { isTyping } = this.state;
		
		  return (
          <div> { isTyping ? <Typing /> : null } <div>
    )}
}
```


And that's all there is to it! 



