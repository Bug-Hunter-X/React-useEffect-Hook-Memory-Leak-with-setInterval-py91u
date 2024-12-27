# React useEffect Hook Memory Leak with setInterval

This repository demonstrates a common error in React applications: memory leaks caused by improper use of the `setInterval` function within the `useEffect` hook.

The `bug.js` file contains a React component with a memory leak, while `bugSolution.js` demonstrates the correct implementation.

## Problem

In the `bug.js` file, the `setInterval` function is used to update a state variable every second. However, it lacks a cleanup function to stop the interval when the component unmounts. This results in a memory leak, where the interval continues to run even after the component is no longer displayed. The continuous incrementing of state will use system resources until the app crashes.

## Solution

The `bugSolution.js` file demonstrates the proper way to handle this issue. A cleanup function is returned from the `useEffect` hook. This function is executed when the component unmounts or when the dependencies change, thus clearing the interval and preventing the memory leak.