Notes for [Eloquent JavaScript](http://eloquentjavascript.net/).

# [1](http://eloquentjavascript.net/chapter1.html). Introduction

## Master Material

> Only continue on when you are reasonably sure you understand the material that came before.

## Punched Cards

> To program early computers, it was necessary to set large arrays of switches in the right position, or punch holes in strips of cardboard and feed them to the computer.

Early computers like the [IBM 1620](http://en.wikipedia.org/wiki/IBM_1620).

Punch holes in [punched cards](http://en.wikipedia.org/wiki/Punched_card).

## ECMAScript

> You should not worry too much about these new versions [of JavaScript such has ECMAScript 5 and ECMAScript harmony] making the things you learn from this book obsolete.

Yeah, don't worry about them one bit.

## Remember to shift+click

> By holding the shift key while pressing the 'run' arrow on a block of code, all blocks before that one will be run as well, so when you start in the middle of a chapter, hold shift the first time you run a piece of code, and everything should work as expected.




# [2](http://eloquentjavascript.net/chapter2.html). Basic JavaScript: values, variables, and control flow

## Sum (`_ + _`) and Concatenation (`_+_`)

> [The `+` operator] concatenates, it glues two strings together.

I use spaces to differentiate numeric `+` from string concatenation `+`.  Spaces for numbers:

	3 + 4

No spaces for strings:

	"str"+"ings"

## Optional Semicolons

> In this book, I won't leave out any semicolons, and I strongly urge you to do the same in your own programs.

Yes, everyone always uses semicolons in JavaScript.  In Java and C++, they're required.

## Optional Block Braces

Although you can leave off braces when a loop (or conditional) only has one statement:

	for (var number = 0; number <= 12; number = number + 2)
		show(number);

I recommend using braces:

	for (var number = 0; number <= 12; number = number + 2) {
		show(number);
	}

The only time I leave off the braces is when the statement is empty:

	// Find the root node of a DOM tree by climbing up the tree until you run
	// out of parent nodes.
	for (var root = node; root.parentNode; root = root.parentNode);

## Equality and Identity

JavaScript has two operators for checking whether two things are the same `==` and `===`.  I always use `===` because `==` sometimes reports `true` at odd times:

	'' == '0'           // false
	0  == ''            // true
	0  == '0'           // true

	false == 'false'    // false
	false == '0'        // true

	false == undefined  // false
	false == null       // false
	null == undefined   // true

	' \t\r\n ' == 0     // true

See [Bad Parts of JavaScript: The Good Parts](http://oreilly.com/javascript/excerpts/javascript-good-parts/bad-parts.html) for this and other parts of JavaScript to avoid.

## `while (true)`

One way to loop until a explicity `break` is with `while (true) {...}`.  Another way is with `for (;;) {...}`.  I prefer the empty `for` myself.




# [3](http://eloquentjavascript.net/chapter3.html) Functions

## Conditional `?:` operator.

I would answer Ex. 3.1 as follows:

	function absolute(x) {
		return x < 0 ? -x : x;
	}

The `?:` operator is handy.

## Pure Functions

Pure functions are a often easier to program with than functions with side effects.  So much so that [some programming langauges](http://haskell.org/haskellwiki/Haskell) only have pure functions.

## Slow and Intuitive: Fast and Convoluted

> In many situations, an elegant, intuitive, and often short solution can be replaced by a more convoluted but faster solution. ... The basic rule, which has been repeated by many programmers and with which I wholeheartedly agree, is to not worry about efficiency until your program is provably too slow. When it is, find out which parts are too slow, and start exchanging elegance for efficiency in those parts.

I also wholeheartedly agree.