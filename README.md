# React useEffect Infinite Loop Bug

This repository demonstrates a common React bug: an infinite loop caused by improper usage of the `useEffect` hook.  The `useEffect` hook, while powerful, can easily lead to infinite render cycles if not used correctly.  This example showcases the issue and its solution.

## Bug Description
The original `MyComponent` function uses `useEffect` to log the current count. However, the dependency array `[]` is empty which triggers it after every re-render, causing an infinite loop.  This will lead to your application crashing or becoming extremely unresponsive.  The browser's console will likely be flooded with log messages.

## Solution
The solution involves correctly specifying the dependency array in `useEffect`. By including `[count]` as the dependency array, the effect only runs when the `count` value changes.  This breaks the infinite loop and results in correct behavior.