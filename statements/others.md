# Other Statement Types

## The Empty Statement

Sometimes you may need a statement that does nothing.
The **empty statement** can be used for this.
It just consists of a single semi-colon.
For example,
sometimes you may want the body of a loop
to do nothing:

```pike
// Keep checking if it is finished, until it is
while (! finished())
  ;
```

## The Block, or Compound Statement

As we have seen above,
you can enclose several statements in curly brackets,
"{" and "}".
The result is called a **block** or **compound statement**,
and can be used as a single statement.
Here is one example:

```pike
{
  write("Hello ");
  write("world!\n");
}
```

Do not put a semi-colon (";")
after the final bracket ("}").

You can define variables inside the block.
Such a variable is local in that block,
and is available only to the program code
written inside the block:

```pike
{
  write("What is your name?\n");
  string name;
  name = Stdio.stdin->gets();
  write("Your name is " + name + ".\n");
}
```

A block can be empty:

```pike
{ }
```

## The Expression Statement

The **expression statement** follows this template:

```pike
*expression* ;
```

That is,
you just take an expression and put a semi-colon (`;`)
at the end.
Typical expression statements are:

```pike
write("Hello world!\n");
i = 7;
++i;
```

All of these are expressions with a semi-colon appended.
Since the expression statement doesn't do anything
with the value of the expression,
it is the so-called "side-effects" of the expressions
that we are interested in.
For example,
the expression "`i = 7`" has the value **7**,
but what is interesting is of course
that it has the side-effect
of setting the variable `i` to **7**.

Since you can take any expression and add a semi-colon,
these strange-looking (and rather useless)
statements are also allowed:

```pike
2 + 2;
3;
```

## Other Statements: `return` and `catch`

The `return` statement is used to leave a method,
and sometimes also to return a value from that method:

```pike
return;
return x + 3;
```

You can read more about the `return` statement
in the chapter about methods.

The `catch` statement is used
to try to execute some Pike code,
letting the programmer control what happens
if there is an error:

```pike
  mixed result = catch
  {
    i = klooble() + 2;
    fnooble();
    j = 1/i;
  };

  if (result == 0)
    write("Everything was ok.\n");
  else
    write("Oops. There was an error.\n");
```

You can read more about the `catch` statement
in the chapter about error handling.
