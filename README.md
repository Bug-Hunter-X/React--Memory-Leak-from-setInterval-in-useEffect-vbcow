# React Memory Leak Example

This repository demonstrates a common React bug: a memory leak caused by improper use of `setInterval` within a `useEffect` hook.  The `bug.js` file contains the faulty code, while `bugSolution.js` provides the corrected implementation.

The issue arises when `setInterval` is used without a cleanup function in `useEffect`. This leads to multiple intervals running concurrently when the component re-renders or unmounts, resulting in a memory leak. The solution showcases the proper usage of `setInterval` with a cleanup function to avoid this problem.

## How to Reproduce

1. Clone the repository.
2. Run `npm install` to install the dependencies.
3. Run `npm start` to start the development server.
4. Observe the increasing counter; leaving the component open for a prolonged period will reveal a memory leak using memory profiling tools. 

## Solution

The solution involves using the return value of the `useEffect` hook to clean up the interval when the component unmounts or when the dependencies change.
