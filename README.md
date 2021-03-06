# jsGotchas

##
1) What would be the output of this code?
```
const a = new Boolean(false);
if(a) {
  console.log("a is true");
}
else {
  console.log("a is false");
}
```

2) What would be the result of the following statement typed in console?
```
{} + []
```

3) How about this one?
```
[] + {}
```

4) Or this?
```
({} + [])
```

Explanation (from SO):
When there is a { at the beginning of a statement, it will be interpreted as a block, which may contain zero or more statements. An block with no statements in it will have an empty continuation value.

In other words, in this case, {} is interpreted as an empty code block.

The statement ends after the ending brace }, which means that the next three characters +[] comprise a statement of their own.

At the beginning of an expression or statement, + is the unary plus operator, which coerces its operand to a number.

So +[] is the same as Number([]), which evaluates to 0.

In short, {} + [] is an empty code block followed by an array coerced to a number.

All that said, if you evaluate {} + [] inside an expression, it will return what you expect:

>> ({} + []) 
"[object Object]" 
Another interesting thing is that you cannot begin a statement with an object literal because the interpreter will try to parse it as a statement. Doing this

{ "object": "literal" };
will throw a syntax error.
