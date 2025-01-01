# React setInterval Memory Leak

This repository demonstrates a common error in React applications: a memory leak caused by the improper use of `setInterval` within a `useEffect` hook.

## The Problem

The `bug.js` file contains a React component that uses `setInterval` to update a counter every second.  However, it's missing a cleanup function within the `useEffect` hook to stop the interval when the component unmounts. This leads to a memory leak because the interval continues to run even after the component is removed from the DOM.

## The Solution

The `bugSolution.js` file provides the corrected version of the component.  The solution introduces a cleanup function that uses `clearInterval` to stop the interval when the component unmounts, thereby preventing the memory leak.

## How to Reproduce

1. Clone the repository.
2. Navigate to the repository's directory in your terminal.
3. Run `npm install` to install the necessary dependencies.
4. Run `npm start` to start the development server.
5. Observe the counter in the browser.  Note that the counter in `bug.js` will continue to increment even after the component is unmounted (e.g. if you navigate away from the page).
6. Check the corrected version in `bugSolution.js` to see the memory leak fix.