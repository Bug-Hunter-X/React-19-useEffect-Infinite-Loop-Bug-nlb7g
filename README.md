# React 19 useEffect Infinite Loop Bug

This repository demonstrates a common error in React 19 involving the `useEffect` hook, leading to an infinite loop.  The issue arises from an improperly defined dependency array or stale closures, resulting in unintended re-renders and potential application crashes.

## Bug Description

The `useEffect` hook, when used without a properly defined dependency array or with stale closures can trigger an infinite loop.  This typically occurs when the effect attempts to update state based on the previous state within the effect itself without declaring the state variable as dependency.  The result is a continuous cycle of updates, consuming significant resources, and potentially crashing the application.

## Reproduction

1. Clone the repository.
2. Navigate to the project directory.
3. Run `npm install` to install the necessary dependencies.
4. Run `npm start` to start the development server.
5. Observe the infinite loop in the console and the application's performance degradation.

## Solution

The solution involves correctly defining the dependency array in the `useEffect` hook.  The array should include all state variables used within the effect.  This ensures the effect is triggered only when the relevant state changes, preventing the infinite loop.  In addition, any closures from outside the functional component must be explicitly included in the dependency array to prevent stale closures.

## Additional Notes

This common bug highlights the importance of understanding the subtleties of the `useEffect` hook and its dependency array.  Carefully managing dependencies is crucial for building robust and performant React applications.