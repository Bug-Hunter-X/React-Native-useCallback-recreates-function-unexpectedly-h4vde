# React Native useCallback Unexpected Recreation

This repository demonstrates a subtle bug in React Native involving the `useCallback` hook.  Even with an empty dependency array, the callback function is recreated when an internal state value is used. This leads to unintended side effects and re-renders.

## Problem

The provided example shows a counter component.  Despite the `useCallback` having an empty dependency array, the increment function is recreated whenever the `count` state changes. This can lead to performance issues and incorrect behaviour.

## Solution

The solution involves correctly specifying the dependencies in the `useCallback` hook, including the state variable used within the callback function.

## How to reproduce

1. Clone this repository.
2. Run `npm install`.
3. Run `npx react-native run-android` or `npx react-native run-ios`.
4. Observe the counter's behavior; it works but illustrates the problem of unnecessary function recreation. 
5. View the 'bugSolution.js' for a corrected implementation. 