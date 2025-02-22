# Unexpected `removeIf` Behavior with Maps and Sets in Kotlin

This repository demonstrates a subtle but potentially problematic behavior of the `removeIf` function when used with `MutableMap` and `MutableSet` collections in Kotlin.  Unlike lists, these collections' iterators are not fail-fast, meaning modifications during iteration might not cause immediate exceptions but can lead to unexpected results.

## The Bug

The `removeIf` function is designed to remove elements from a collection that satisfy a given predicate.  However, when used with maps and sets, modifications during iteration may not behave as intuitively expected, because the iterator may skip elements as a result of the changes.

## The Solution

The solution involves using a different approach that ensures all elements are correctly processed before any removals are made.

## How to Run

1. Clone this repository.
2. Open the project in your preferred Kotlin IDE (IntelliJ IDEA, etc.).
3. Run the `bug.kt` and `bugSolution.kt` files.  Observe the different outputs and behaviors.