## Syntax
There are multiple flavours of regex but every flovour has a *common ground*.



## Useful Regex

To change from `@RequestMapping` to `@XxxMapping` use the following regex:
```
@w+[M]\w*\(((.*"),(.*RequestMethod\W(.{1})(\w+)))
```
And replace the content of the line with the following:
```
@$4\L$5Mapping($2
```