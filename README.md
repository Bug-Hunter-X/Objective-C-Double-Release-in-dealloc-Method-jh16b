# Objective-C Double-Release Bug

This repository demonstrates a subtle but dangerous bug in Objective-C related to double-releasing objects within the `dealloc` method.  This can lead to crashes or undefined behavior, often appearing much later in the execution flow, making it difficult to track down.

The `bug.m` file contains the erroneous code. The `bugSolution.m` file offers a corrected version. This illustrates how to prevent this bug.

## Reproduction Steps

1. Clone the repository
2. Build and run the buggy code (bug.m)
3. Observe the crash or unpredictable behavior
4. Compare with the corrected version (bugSolution.m) to see the fix

## Key Concepts

* **Memory Management:** Understanding Objective-C's memory management rules is crucial for avoiding issues like double releases.
* **`dealloc` Method:**  The `dealloc` method should only release objects that the class owns.  Never release an object more than once.
* **ARC and Manual Memory Management:** The issue, while less common with Automatic Reference Counting (ARC), can still occur if not properly handled, particularly when working with legacy code.