This repository correspond to the TDD Calculator assignment.

## Setup

### Environment

- Node v14: https://nodejs.org/en/
  (alernative if Mac/Linux https://github.com/nvm-sh/nvm )
- Yarn: https://yarnpkg.com

### Setup

Once you download it, add all libraries by executing:

```zsh
$ yarn
```

### Run

```zsh
$ yarn test
```

The initial test result is the following:

```
 FAIL  src/calculator.spec.js
  ✕ 1 | "" (1ms)

  ● 1 | ""

    TypeError: _calculator.Calculator is not a constructor

       7 |   ${1}  | ${""}
       8 | `('$order | "$sequence"', ({ sequence }) => {
    >  9 |   expect(new Calculator()).toSatisfy(sequence)
         |          ^
      10 | })
      11 |
      12 | /*

      at src/calculator.spec.js:9:10

Test Suites: 1 failed, 1 total
Tests:       1 failed, 1 total
Snapshots:   0 total
Time:        0.375s, estimated 1s
Ran all test suites related to changed files.

Watch Usage: Press w to show more.
```

## Instructions

### Operators

You can use javascript native operators for addition and multiplication.

### Transformations

See https://www.youtube.com/watch?v=VW4hHaid3PE

When refactoring or fixing a test in production code,
pick always the first transformation of the following
list:

1. Null
2. Null to Constant
3. Constant to Variable
4. Add Computation
5. Split Flow
6. Variable to Array
7. Array to Container
8. If to While
9. Recurse
10. Iterate
11. Assign
12. Add Case

This is not mandatory, it is just a hint.

### Tests

Tests are already written.
You have to write no tests.

There is only one test function call,
which executes a table of tests.

Initially there is only one table test line.
The rest of lines that you have to execute
are below in a comment.

### Order

There are test table lines inside a comment below
the test function call.

This comment contains all test table lines
that you have to implement.
Each line has an order number that you have to respect.

In order to complete the assignment
move one by one
to the test function call
and solve each before passing to the next one.
Ex:

```javascript
test.each`
  order | sequence
  ${1}  | ${""}
`('$order | "$sequence"', ({ sequence }) => {
  expect(new Calculator()).toSatisfy(sequence)
})

/*
  order | sequence
  ${2}  | ${"[0]"}
  ${3}  | ${"0[0]"}
  ${4}  | ${"1[1]"}
  ${5}  | ${"12[12]"}
  ...
```

Once the first is solved, copy the next test, and make it pass:

```javascript
test.each`
  order | sequence
  ${1}  | ${""}
  ${2}  | ${"[0]"}
`('$order | "$sequence"', ({ sequence }) => {
  expect(new Calculator()).toSatisfy(sequence)
})

/*
  order | sequence
  ${3}  | ${"0[0]"}
  ${4}  | ${"1[1]"}
  ${5}  | ${"12[12]"}
  ...
```

And so on:

```javascript
test.each`
  order | sequence
  ${1}  | ${""}
  ${2}  | ${"[0]"}
  ${3}  | ${"0[0]"}
`('$order | "$sequence"', ({ sequence }) => {
  expect(new Calculator()).toSatisfy(sequence)
})

/*
  order | sequence
  ${4}  | ${"1[1]"}
  ${5}  | ${"12[12]"}
  ...
```

Continue in order until implementing all test table lines inside the comment.

**Important**:
Follow the exact order and fix
the minimal amount of your production code
in order to pass the test.

Only the tests starting with one space in the sequence
are redundants, expect them to pass directly without
implementing any code.

### Commits

You have to do a commit for each test that you pass.
Name the commit as: "Test table line X"
where X is the test table line order number.

If you forgot to commit,
undo the changes,
reset to a previous commit,
and redo again from the last correct commit.

Be careful, your grade depends on this.

### Help

Convert a string to number with `+`:

```javascript
const string = "12";
const number = +string;
expect(string + 3).toBe("123");
expect(number + 3).toBe(15);
```

Concatenate number multiplying \* 10:

```javascript
const number = 12;
const digit = 3;
expect(number * 10 + digit).toBe(123);
```

Learn Javascript details here:

- https://github.com/drpicox/learn-javascript-bytesting-jest

_Before asking any question about javascript, provide a clone of the repository solved_.

### Grades

This practice evaluates how good are you following TDD.

For this reason,
the teacher will subsitute the testing file by its own,
and will test commit by commit
to know how you have been progressing in the implementation.

Your **grade can be reduced by** the following parameters:

- you do not pass secret teacher tests (extra checks that logic is correct),
- you pass too many commits at once,
- you skip the order and solve test table lines out of order,
- you do not **keep a clean production code** at all times,

Expect to have a 0:

- do not do TDD
- you change the expected API for the Calculator class (it emerges from tests)
- you use the `eval` function or any library to solve it

Expect to have a 0 in this assignment and 0 as final grade if:

- you cheat (copy from other colleages or copy a solution from internet)

The **maximum grade** that you can aspire is the number of order \* 0.2. So if you achieve order 25 you may have a 5, if you acieve order 50, you may have a 10. Remember that reaching the implementation until that order do not guarantee the maximum grade.
