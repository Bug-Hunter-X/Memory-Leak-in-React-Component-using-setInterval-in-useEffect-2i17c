# React UseEffect setInterval Memory Leak
This repository demonstrates a common mistake when using `setInterval` within a React `useEffect` hook: forgetting to clean up the interval when the component unmounts. This leads to a memory leak, as the interval continues to run even after the component is no longer needed. 

The `bug.js` file contains the buggy code, while `bugSolution.js` shows the corrected version.

## How to reproduce the bug
1. Clone this repository.
2. Run `npm install`.
3. Run `npm start`.
4. Observe the counter continuously increasing.  Even if you navigate away from the page, the counter will keep updating. This is the memory leak.

## How the solution works
The solution uses the return value of `useEffect` to implement a cleanup function. This function clears the interval when the component unmounts, preventing the memory leak.