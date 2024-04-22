# Simple Scripting Language (SSL)

One of the project I.ve wanted to undertake for a while now is writing a simple programing language.

## Requirements

- Variables/Literals `let a = 1`
- Integers, Booloean, Strings
- Block Based
- if/else: `if else`
- comparison operators: `== != > >= < <=`
- boolean operators: `|| && !`
- mathematical operators: `+ - / * ** %`
- print: `print`

## Example

```rust
let foo = "foo"

let bar = if foo == "foo" {
  true
} else {
  false
}

print bar
```

## Abstract Syntax Tree
```javascript
body [
  assignment: {
    variable: "foo",
    value: literal { "foo" },
  },
  assignment {
    variable: "bar",
    value: if_statement {
      condition: bin_op {
        op: "equals",
        a: variable { "foo" },
        b: literal { "foo" },
      },
      branch: [
        literal { true },
      ],
      else: [
        literal { false },
      ],
    },
  },
  print {
    args: variable { "var" },
  },
]
```
