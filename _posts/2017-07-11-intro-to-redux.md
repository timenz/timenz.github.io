---
layout: post
title: Intro to Redux
date: 2017-07-11 18:29:57
tags: [coding, javascript, react]
---


> Every state that you ever been is that define who you are today

In recent days seems everyday came new cool stuff in javascript word, one of them is Redux and today we will have a little introduction with Redux. Redux basically is a flux implementation and what is Flux, Flux is an architecture not a framework not library, that used by [React](https://facebook.github.io/react/) of Facebook, Flux architecture using concept of Unidirectional Data Flow, this concept allow element to receive event from other element even between them not connected directly<!-- more -->. I will not going further with flux because mostly of them will covered with redux in the next section.

Redux is simplified the implementation of Flux, unlike Flux that allow us to create many store object, Redux using single source of truth for UI state, but most awesome of Redux is implementation of immutability concept. Immutability is a concept in functional programming, concept that honor every state of the object after they mutated or changed. In a broad language we can explain this concept like ‘You were hungry and then you order the pizza, after the pizza delivery came and you ate 3 slice of pizza now you fell satiated, even now you full its not change the fact that you were hungry some minutes ago’

With Flux and immutability concept combined in Redux, every state changing in application is predictable, after an application got some state change and if you want to going back to cancel some state change you will get the predicted state and also with predictable state its make easier for us to create the testing unit. Redux has an awesome [devtool](https://github.com/gaearon/redux-devtools), this tool allow us to inspect state change in the Redux application you can time traveling going back and forward changing some element, disabled or insert some state change to create another predicted reality.

Cool, right ?

So lets begin to explore under the hood of Redux, the core concept of Redux consist of 3 element:

- Store
- Action and action creators
- Reducers


![http://slides.com/jenyaterpil/redux-from-twitter-hype-to-production#/9](https://d2mxuefqeaa7sj.cloudfront.net/s_22C2BCD3EFB77526DD39FB0843005F1C691CF42D04462473FD9617974903E57F_1494743672708_ARCH-Redux2-real.gif)


Animation above show us the concept of Redux application, to understand that animation its better to know the every part of Redux core.


## Store

Store basically is the Redux itself, its wrapping a javascript object that called state, other than state store has two key methods : `getState()` and `dispatch()` to get state object and dispatch action to the reducer.


## Actions

In the source action just method that return javascript object, and the only required field in that object is `type`, other than type action also may carry payload some data to processed in reducers.

```
export const toggleTodo = (id) => {
  return {
    type: 'TOGGLE_TODO',
    id
  }
}
```

## Reducers

In the source code reducers is switch statement on incoming `action.type` and reducers must return new copies of state that reflect changes.

```
const todo = (state = {}, action) => {
  switch (action.type) {
    case 'TOGGLE_TODO':
      if (state.id !== action.id) {
        return state
      }

      return Object.assign({}, state, {
        completed: !state.completed
      })
  }
}
```

Other than 3 element above an Redux application may also contain Middleware, middleware works like filter that can prevent an actions from reaching the reducers.

And thats all guys about our little introduction with Redux, you may getting started your first Redux application go ahead at http://redux.js.org/. Thank you for reading.

library

- https://www.slideshare.net/tedpennings/how-to-redux/2
- https://medium.com/javascript-scene/the-dao-of-immutability-9f91a70c88cd
