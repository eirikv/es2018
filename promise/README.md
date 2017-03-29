# Promise.prototype

## finally

Many promise libraries have a "finally" method, for registering a callback to be invoked when a promise is settled (either fulfilled, or rejected). The essential use case here is cleanup - I want to hide the "loading" spinner on my AJAX request, or I want to close any file handles I’ve opened, or I want to log that an operation has completed regardless of whether it succeeded or not.

promise.finally(func) is similar to promise.then(func, func), but is different in a few critical ways:

* When creating a function inline, you can pass it once, instead of being forced to either declare it twice, or create a variable for it
* A finally callback will not receive any argument, since there's no reliable means of determining if the promise was fulfilled or rejected. This use case is for precisely when you do not care about the rejection reason, or the fulfillment value, and so there's no need to provide it.
* Unlike Promise.resolve(2).then(() => {}, () => {}) (which will be resolved with undefined), Promise.resolve(2).finally(() => {}) will be resolved with 2.
* Similarly, unlike Promise.reject(3).then(() => {}, () => {}) (which will be resolved with undefined), Promise.reject(3).finally(() => {}) will be rejected with 3.

Source:
[TC-39](https://github.com/tc39/proposal-promise-finally)
