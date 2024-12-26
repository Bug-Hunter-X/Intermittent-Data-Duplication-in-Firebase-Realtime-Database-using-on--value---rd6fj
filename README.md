# Firebase Realtime Database Data Duplication Bug

This repository demonstrates a bug encountered while using Firebase Realtime Database's `on('value', callback)` method. Under specific conditions, the callback function is triggered multiple times, leading to data duplication.

## Bug Description
The `on('value')` listener repeatedly calls the callback function, causing redundant updates to the database.  This is an intermittent issue, making it difficult to reproduce consistently.

## Reproduction Steps
1. Clone this repository.
2. Configure your Firebase project and add credentials.
3. Run `bug.js`.
4. Observe the data in the Firebase Realtime Database. You should see duplicated data under specific circumstances. (described further in bug.js comments)

## Solution
The solution involves using `once()` to read data instead of `on()`.   See `bugSolution.js` for the corrected code.

## Additional Notes
This bug highlights the importance of carefully managing event listeners in Firebase Realtime Database and using appropriate methods for reading and updating data to prevent unexpected behavior. 