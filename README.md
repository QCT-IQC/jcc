# jcc
##Reversible Circuit Compiler 

This compiler is based on a slightly modified version of the Janus programming langange.
Below are some references:

- [A reversible programming language and its invertible self-interpreter](http://doi.acm.org/10.1145/1244381.1244404)
- [JANUS: A Time-Reversible Language](http://www.tetsuo.jp/ref/janus.pdf)

##Installing

Create a sandbox (recommended) with:

`cabal sandbox init`

Install dependencies:

`cabal install --dependencies-only`

Now build the actual project using:

`cabal build`

It will place the jcc binary in `dist/build/jcc/jcc`.

##Useage

For help use:

jcc -h 

Currently a semicolon is needed after each statement.
This will hopefully be fixed when I have time to update the parser.

Not all operations are yet supported.

Due to the compilation target (no-feedback circuit model), loops are only planned to be supported in the case where they have fixed bounds.
For that same reason procedures might be supported in the future but recursive calls will not be.

For example try: 

```
x1 x2;
x1 += x2;
x2 ^= x1;
```

Note if-statments are currently implemented but do not work correctly.
This will be fixed when hadamard gates are added to the gate set and simulator.

Check the [webpage](http://aparent.github.io/jcc/) for example output.
