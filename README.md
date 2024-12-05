# React useEffect Infinite Loop Bug

This repository demonstrates a common error in React's `useEffect` hook: creating an infinite loop by incorrectly updating state within the effect without specifying dependencies.  The `bug.js` file contains the buggy code, while `bugSolution.js` provides the corrected version.

## Problem
The original code attempts to increment a counter within the `useEffect` hook without specifying dependencies. This causes the component to re-render continuously because the state update triggers the effect again, and the cycle repeats.

## Solution
The solution involves correctly managing the dependencies in the `useEffect` hook's second argument.  By including `count` as a dependency (or removing the state update from within the useEffect), we only update the count under the right circumstances, preventing the infinite loop.