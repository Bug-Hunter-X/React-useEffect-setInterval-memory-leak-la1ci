# React useEffect setInterval memory leak
This example demonstrates a common mistake when using the setInterval function within a React useEffect hook.  Forgetting to clear the interval before the component unmounts results in a memory leak. The solution shows how to properly clean up using clearInterval.

## Bug
The bug is in the `MyComponent` function. The `setInterval` function is called inside of `useEffect` but does not have a mechanism to stop the timer.  This will continue to increment the `count` even after the component is unmounted, causing a memory leak.

## Solution
The solution shows how to properly handle the `setInterval` function within `useEffect`. We store the returned interval ID from `setInterval` and clear the interval using `clearInterval` inside the return function of `useEffect`, thereby preventing the memory leak.
