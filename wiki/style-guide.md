# Company Style Guide

## Python Style Guide

### Tabs or Spaces?

Spaces all the way. 4 spaces should be used for each indentation level.

### Indentation Style

In the case of a continuation line, an extra level of indentation should
be added.

```
# Good
def long_function_name(
        var_one, var_two
        var_three, var_four):
    print(var_one)

foo = long_function_name(
    var_one, var_two,
    var_three, var_four
)
```

This is better than aligning the continuation lines:
```
# Bad
def long_function_name(var_one, var_two
                       var_three, var_four):
    print(var_one)
```

Adding an extra level of indentation saves programmers the hassle of
having to realign the continuation lines if the function name changes.

```
# Good
def long_long_function_name(
        var_one, var_two
        var_three, var_four):
    print(var_one)
```

vs.

```
# Bad
def long_long_function_name(var_one, var_two
                            var_three, var_four):
    print(var_one)
```

### Quoting

Single quotes are preferred over double quotes for strings. If, however,
the string contains a single quote, then double quotes should be used to
avoid having to escape the single quote. Additionally, doc-strings or
multi-line comments should use double quotes.

### Naming Conventions

PascalCase should be used for Python classes, while snake\_case should be
used for variable, function, and method names.

```
class MissingBracket:
    def __init__(members):
        this.members = members

missing_bracket = MissingBracket([])
```

### Etc.

There's a lot more, but the above paragraphs cover most of the main Python
coding conventions for Missing Bracket. Missing Bracket's other Python coding
conventions is covered at these links.

- [Django](https://docs.djangoproject.com/en/dev/internals/contributing/writing-code/coding-style/)
- [Django on quotes](https://code.djangoproject.com/ticket/27655)
- [PEP8](pep8.org)

## Javascript/JSX Style Guide

### Basic Rules for Both Javascript/JSX

#### Naming Conventions

- **Plain Javascript files**: Should have a regular `.js` extension
- **React component files**: 
  - **Extension**: the `.jsx` extension should always be used.
  - **Filename**: PascalCase should always be used
- **React components**: PascalCase should always be used (e.g. `ReservationCard`)
- **All other things**: camelCase should always be used. 

### Plain Javascript

#### Indentation Style

The indentation style for Javascript is the same as Python.

```
// Bad
function longFunctionName(varOne, varTwo
                          varThree, varFour) {
    console.log(varOne);
}


// Good
function longFunctionName(
        varOne, varTwo
        varThree, varFour) {
    console.log(varOne);
}

// Good
foo = longFunctionName(
    varOne, varTwo,
    varThree, varFour
);

```

#### Quotes

Single quotes should be used, unless the string contains a single quote. Then
double quotes should be used to avoid having to escape the single quote.

### JSX Conventions

#### Alignment
Component prop attributes should have their own line, with a hanging indent of two spaces.
If props can fit on the same line line as their element, then the element and props should
be on the same line. The children of a React element should have a normal hanging indent
of two spaces.

```
// Bad
<Foo superLongParam="bar"
     anotherSuperLongParam="baz" />

// Good
<Foo
  superLongParam="bar"
  anotherSuperLongParam="baz"
/>

// Good
<Foo bar="bar" />

// Good
<Foo
  superLongParam="bar"
  anotherSuperLongParam="baz"
>
  <Quux />
</Foo>
```

#### JSX props/attributes

Double quotes should be used for JSX attributes, since
the convention for regular HTML element attributes uses
double quotes.

#### Multi-line Components

Multi-line components should be wrapped in parentheses.

```
// bad
render() {
  return <MyComponent variant="long body" foo="bar">
           <MyChild />
         </MyComponent>;
}

// good
render() {
  return (
    <MyComponent variant="long body" foo="bar">
      <MyChild />
    </MyComponent>
  );
}

// good, when single line
render() {
  const body = <div>hello</div>;
  return <MyComponent>{body}</MyComponent>;
}
```

#### Spacing

Self-closing tags should have a single space.

```
// bad
<Foo/>

// very bad
<Foo                 />

// bad
<Foo
 />

// good
<Foo />
```

Curly braces should not be padded with extra spaces.

```
// bad
<Foo bar={ baz } />

// good
<Foo bar={baz} />
```

#### Tags

Tags with no children should be self-closed. If, however, the tag
has multi-line properties, then the tag should be closed on a new
line.

```
// bad
<Foo variant="stuff"></Foo>

// good
<Foo variant="stuff" />

// bad
<Foo
  bar="bar"
  baz="baz" />

// good
<Foo
  bar="bar"
  baz="baz"
/>
```

### Etc.

The Javascript style guide is an attempt at summarizing Airbnb's style guide:
[Airbnb style guide](https://airbnb.io/javascript/react/#spacing)


