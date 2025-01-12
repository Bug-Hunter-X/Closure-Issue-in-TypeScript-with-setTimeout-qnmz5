# TypeScript Closure Issue with setTimeout

This repository demonstrates a common error related to closures in JavaScript/TypeScript when using `setTimeout` within a loop.  The example shows how the loop variable's value is unexpectedly captured by the closure.

## Bug Description

The `printNumbers2` function aims to print numbers from 1 to `n` with a 1-second delay between each number using `setTimeout`.  Due to how closures work, each `setTimeout` callback function captures the final value of `i` (which is `n+1`), resulting in the incorrect output.

## Solution

The solution involves using an immediately invoked function expression (IIFE) to create a new scope for `i` within each iteration of the loop, ensuring each callback function captures the correct value of `i` at the time of its creation.