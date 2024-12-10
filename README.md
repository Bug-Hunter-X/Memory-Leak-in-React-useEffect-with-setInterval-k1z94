# React useEffect setInterval Memory Leak
This repository demonstrates a common mistake when using the `useEffect` hook with `setInterval` in React.  The code incorrectly manages the interval, leading to a memory leak.

## Problem
The original `MyComponent` function uses `setInterval` to update a counter every second. However, it fails to clear the interval when the component unmounts, resulting in a memory leak and potentially unexpected behavior.

## Solution
The `bugSolution.js` file provides a corrected version of the component.  The key change is adding a cleanup function to the `useEffect` hook's return value.  This cleanup function ensures that `clearInterval` is called when the component is unmounted, preventing memory leaks.

This example highlights the importance of proper cleanup in React's lifecycle methods, especially when using timers or other long-running processes.