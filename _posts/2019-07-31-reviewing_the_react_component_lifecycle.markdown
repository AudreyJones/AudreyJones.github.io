---
layout: post
title:      "Reviewing the React Component Lifecycle"
date:       2019-08-01 03:11:03 +0000
permalink:  reviewing_the_react_component_lifecycle
---

React, a JavaScript framework, used to build user interfaces uses what are called components and the DOM, or the Document Object Model -- a virtual representation of a webpage. React Components are have the minimal structural requirement that they are only required to have a render method. In their render method, React components take in input data and output a display using JSX, which is an XML-like syntax that makes the inputted data accessible via ```this.props``` (The this in this case -- pun not intended -- is the JavaScript way of referring to the component itself!)

React components can also hold and access data via what's referred to as a state. A component's state is simply a plain ole' JavaScript object (or "POJO", as Flatiron seems to lovingly call them) that can hold data. A component's state can be accessed via ```this.state``` (which translates to this (particular component's) state). Each time that a component's state is updated, it is re-rendered. Easy, right?

React components also have heredity, in which we can have "parent components", which pass information down to their children in the form of props, and those "child components" are said to have inherited that information from their parent components -- very similar to human beings! Also like humans, React components have a lifecycle. They progress through different phases and during each phase, specific methods are available and/or enacted. The three phases of a React component lifecycle are:

Mounting: when a component is created and inserted into the DOM

Updating: when the component's state or props are updated

Unmounting: when a component is removed from the DOM

Googling 'react component lifecycle' brings up many awesome links on the component lifecycle, but I find that I am much more of a visual learner, so I tend to gravitate to more of the graphical representations of concepts. Below are the three Lifecycle phases and the methods that run in each of them (and of course, what they do):

Mounting
* **constructor()**: called prior to mounting, the constructor method initializes state in the component and enables you to bind event handler methods to an instance of the component

* **static getDerivedStateFromProps()**: is run just prior to render() -- initially (and before every subsequent re-rendering)

* **render()**: the actual mounting of the component to the DOM

* **componentDidMount()**: fired after any rendering of a component initially (and after every subsequent re-rendering) to the DOM; usually used to set up async processes (like an HTTP fetch request for data on an external server) -- where we can specify how to handle long-running processes (i.e: loading vs making available data that we've fetched) -- to have something to return to the user at all times.


Updating

* **shouldComponentUpdate()**: invoked prior to re-rendering; compares old and current props and state to prevent any unnecessary re-rendering

* **getSnapshotBeforeUpdate()**: returns a "snapshot" of the the component (i.e: scroll position, or any other tracked attributes of the component) that can be utilized by the **componentDidUpdate** method (following the next render)

* **static getDerivedStateFromProps()**: is run just prior to render() -- initially (and before every subsequent re-rendering); used rarely to define state changes to prepare for updating

* **render()**: the actual mounting of the component to the DOM
 
* **componentDidUpdate()**: fired just after the component is re-rendered, or updated. Accepts the snapshot returned by **getSnapshotBeforeUpdate**.

Unmounting
* **componentWillUnmount()**: runs just prior to the component being removed, or unmounted, from the DOM. Prevents additional data for and from the component from being fetched.
