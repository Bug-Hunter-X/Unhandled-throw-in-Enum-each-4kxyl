# Elixir Enum.each and throw

This example demonstrates an uncommon error related to the use of `throw` inside an `Enum.each` loop in Elixir.  The code attempts to stop iteration when a specific condition is met, but the use of `throw` causes unexpected behavior.

## Bug

The bug lies in using `throw` within `Enum.each`. While `throw` functions as intended in stopping further iterations, it also abruptly halts the `Enum.each` function itself.  As a result, code intended to execute after `Enum.each` is skipped.

## Solution

The ideal solution would involve restructuring the code to avoid the need for `throw` within `Enum.each`.  Alternatively, the code can be modified to use a try-catch block to gracefully handle the `throw` and execute the remaining code.