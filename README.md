# React Native: Accessing State or Props Before Component Mount

This repository demonstrates a common error in React Native: attempting to access component state or props before the component has finished mounting. This can occur when asynchronous operations (e.g., data fetching) are involved, leading to unexpected behavior or crashes.  The `Bug.js` file showcases the problematic code, while `BugSolution.js` provides a corrected version.

## Problem

In the original code (`Bug.js`), we attempt to access and use data from an asynchronous API call before the component's state has been updated.  This leads to `undefined` values or runtime errors.

## Solution

The solution (`BugSolution.js`) uses the `useEffect` hook to handle the asynchronous operation and ensures the data is available before use. The `useEffect` hook's second argument ensures the effect runs only once after the component mounts.   This approach prevents attempts to use the data before it's ready. We also use optional chaining (`?.`) to gracefully handle the case where data might still be loading.