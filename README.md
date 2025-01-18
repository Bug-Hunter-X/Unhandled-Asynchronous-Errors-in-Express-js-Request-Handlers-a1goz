# Unhandled Asynchronous Errors in Express.js Request Handlers

This repository demonstrates a common, yet easily missed, error in Express.js applications: unhandled asynchronous errors within request handlers.  When an asynchronous operation within a route handler throws an error and isn't caught, the error isn't handled gracefully, potentially leading to application crashes or unexpected behavior. 

The `bug.js` file shows an example where an asynchronous operation (`someAsyncOperation`) throws an error.  However, the `catch` block within the `.then()`/.`catch()` chain is empty, resulting in unhandled promise rejection. This is a silent failure that won't be reported to the console unless a process-level unhandledRejection event listener is active.

The `bugSolution.js` file presents the corrected version with proper error handling, providing a better user experience and application stability. 