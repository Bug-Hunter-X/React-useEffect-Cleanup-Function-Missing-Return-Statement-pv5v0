# React useEffect Cleanup Function Missing Return Statement

This example demonstrates a common mistake in React's `useEffect` hook: forgetting to return a cleanup function.  This can lead to memory leaks and unexpected behavior, especially when dealing with event listeners or other side effects.

## The Problem

The `bug.js` file shows a component that adds an event listener using `addEventListener` inside the `useEffect` hook. However, it's missing the crucial return statement that provides a cleanup function.  Without this, the event listener will persist even after the component unmounts, potentially causing unexpected behavior or memory leaks.

## The Solution

The `bugSolution.js` file demonstrates the correct way to handle this.  A cleanup function is returned from `useEffect`, which removes the event listener when the component unmounts using `removeEventListener`. This ensures proper cleanup and prevents potential problems.

## How to reproduce

1.  Clone this repository
2.  Run `npm install`
3.  Run `npm start`
4. Observe the behavior of the bug and the fix

## Learning Points

Always remember to include a cleanup function within your `useEffect` hook when using `addEventListener`, `setInterval`, `setTimeout`, or any other operation that needs to be cleaned up when the component unmounts.