Its a small program made in any language that targets an specific function or feature.

Most of the scripts don't have an *UI* because they run in the *background*. Some scripts have an *TUI*.

To be able to run an *script* it'll depend on the language used to make it. 

## Schema
In *Unix* based systems every script and interpreted program has to follow the following schema:

```text
#shebang

...Code...
```

## Example

The following script (`script1`) is an example made in [[Python]]:

```python
#!/usr/bin/python3

def hello:
  print("Hello World!")

hello()
```

And to run it:
```shell
python script1.py
```
And it generates the following output:
```text
> Hello World!
```
