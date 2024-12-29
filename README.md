# Unexpected NaN with Loose Equality and Null/Undefined

This repository demonstrates a common JavaScript bug related to loose equality (==) when handling null and undefined values. The `foo` function intends to return 0 if the input is null, but it fails to correctly handle undefined, resulting in NaN.

## Bug Description
The `foo` function uses loose equality (`==`) to check if the input `x` is null.  While this works for null, loose equality considers `undefined` to be loosely equal to neither null nor 0. This leads to `undefined + 1` which evaluates to `NaN`.

## Solution
The solution uses strict equality (`===`) to explicitly check for both null and undefined, ensuring that the function returns the expected value in both cases.