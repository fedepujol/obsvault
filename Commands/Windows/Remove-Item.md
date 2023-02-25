# Remove-Item
Windows implementation of Linux `rm`. It's been alias to `rm` for Unix users. 

## Flags
-r Recursive
-fo Force

## Usage
`Remove-Item /r /fo xxx`

## Faq
- I can't use `rm -rf` because it raises an error.
To delete recursively a directory you must use `rm -r -fo`
