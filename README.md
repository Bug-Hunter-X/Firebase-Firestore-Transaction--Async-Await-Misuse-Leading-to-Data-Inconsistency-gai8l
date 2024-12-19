# Firebase Firestore Transaction: Async/Await Misuse

This repository demonstrates an uncommon error in Firebase Firestore transactions related to the incorrect handling of asynchronous operations, specifically using promises within `runTransaction`.  Improperly handling the promise returned by `transaction.get()` can lead to inconsistent data updates.

The `bug.js` file shows the incorrect implementation, where the promise from `transaction.get()` is not correctly awaited, resulting in the transaction potentially using outdated data.

The `bugSolution.js` file presents the corrected code using `async/await` to ensure the transaction operates on the most up-to-date data.

## How to Reproduce

1.  Clone this repository.
2.  Set up a Firebase project and configure the necessary credentials.
3.  Run the `bug.js` and `bugSolution.js` files to observe the differences in behavior.  Observe the inconsistent updates caused by improper async handling.