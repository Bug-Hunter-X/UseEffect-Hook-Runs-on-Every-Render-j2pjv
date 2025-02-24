# React useEffect Hook Runs on Every Render

This repository demonstrates a common issue with the React `useEffect` hook where an effect with an empty dependency array still runs on every render. This can lead to unexpected behavior and performance issues.

## Problem

The provided code intends for the `useEffect` hook to run only once, upon mounting the component. However, due to an error in state management (or other scenarios), it runs after every render, creating a loop.  The `console.log` statements show this unexpected behavior.

## Solution

The solution involves ensuring the dependencies array is accurate and includes values that when changed, cause the effect to re-run. If there are no dependencies (and the effect does not change the component's state or effect external APIs/state), the correct usage is to avoid the dependency array altogether.