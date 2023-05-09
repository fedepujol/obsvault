Regular Expressions (shorten as **regex**, or **regexp**) are a sequence of characters that use *pattern matching* in text. This *pattern matches* is used in *string-based algorithms*.

## Syntax
There are multiple syntaxes (dated since 1980) of regex but everyone has a *common ground*.

### Modifiers
There are *quantifiers* and *matchers* modifiers and a few *wildcadrs*.

#### Matchers
`|` Boolean **or**
`[]` or `()` for Grouping.
`.`: Any character except newline.

##### Scape Matchers
The *scape* character depends of the syntax (Unix, Perl, etc).

The most common scape character is the backslash (`\`). [[Lua]] has a percentage sign (`%`) as a scape.

`\w`: Words only.
`\d`: Digits only.
`\s`: Space characters.
`\n`: Newline.
`\t`: Tabs.
`\r`: Carriage return.

#### Quantifiers
`?`: One or zero matches.
`*`: One or more matches.
`+`:  Zero or more matches.
`{}`: Number of matches.

#### Anchors
`^`: Start of a string.
`$`: End of a string.

#### Lookaround
`(?=abc)`: Positive look ahead.
`(?!abc)`: Negative look ahead.

## Examples

To change from `@RequestMapping` to `@XxxMapping`. Will be using *find and replace*.

```java
@RequestMapping(value = "/example", RequestMethod.GET)
```

The find *regex* could be the following:
```regex
@w+[M]\w*\(((.*"),(.*RequestMethod\W(.{1})(\w+)))
```

And in the replace section:
```regex
@$4\L$5Mapping($2
```

When executed in the code, we get the following change:
```java
@GetMapping(value = "/example")
```