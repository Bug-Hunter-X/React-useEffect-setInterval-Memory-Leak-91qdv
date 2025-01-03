# React useEffect setInterval Memory Leak
This example demonstrates a common mistake when using the `setInterval` function within the `useEffect` hook in React.  Forgetting to include a cleanup function leads to a memory leak, as the interval continues to run even after the component unmounts.

## Bug
The `bug.js` file contains a component that increments a counter every second using `setInterval`. However, it fails to provide a cleanup function within the `useEffect` hook to stop the interval when the component unmounts. This results in the interval continuing indefinitely, leading to a memory leak.

## Solution
The `bugSolution.js` file shows the corrected version.  A cleanup function is added using the return statement within the `useEffect` hook, ensuring the `clearInterval` function stops the interval when the component is unmounted.