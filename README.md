<div align="center">
	<h1>Roblox Luau Promise</h1>
	<p>An implementation of <code>Promise</code> similar to Promise/A+.</p>
	<a href="https://eryn.io/roblox-lua-promise/"><strong>View docs</strong></a>
</div>
<!--moonwave-hide-before-this-line-->

## Why you should use Promises

The way Roblox models asynchronous operations by default is by yielding (stopping) the thread and then resuming it when the future value is available. This model is not ideal because:

- Functions you call can yield without warning, or only yield sometimes, leading to unpredictable and surprising results. Accidentally yielding the thread is the source of a large class of bugs and race conditions that Roblox developers run into.
- It is difficult to deal with running multiple asynchronous operations concurrently and then retrieve all of their values at the end without extraneous machinery.
- When an asynchronous operation fails or an error is encountered, Lua functions usually either raise an error or return a success value followed by the actual value. Both of these methods lead to repeating the same tired patterns many times over for checking if the operation was successful.
- Yielding lacks easy access to introspection and the ability to cancel an operation if the value is no longer needed.

This Promise implementation attempts to satisfy these traits:

* An object that represents a unit of asynchronous work
* Composability
* Predictable timing

## FORKED VERSION

This is a forked version of [Evaera's Promise library](https://github.com/evaera/roblox-lua-promise) with type annotations added to allow this library to be used in a strict-mode [Luau](https://luau-lang.org) project. Type annotations are imperfect due to limitations with the Luau language, but should at least cover intellisense and basic static analysis.

Please notify me through the issues section if any issues are encountered related to type safety or crashes. Otherwise, please send any issues related to runtime behavior to the [original repository](https://github.com/evaera/roblox-lua-promise), being mindful of differences between this library and the original library.
