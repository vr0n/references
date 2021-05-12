# Shell/GNU tool command references

## csplit
```sh
# split a file at a particular line
# --digits: number of digits at end of new file (i.e., out00 versus out000)
# --quiet: supress output
# --prefix: output file name prefix (i.e, out00 versus file00)
csplit --digits=2 --quiet --prefix=out <file> "/<character sequence/" "{*}"
```
## rsync
```sh
# --progress should just be aliased in rsync, as it is awesome
# -r to recursively copy files if copying a directory
# if copying a directory, a trailing slash will copy the directories contents in full. No trailing slash will just copy the directory and its contents
rsync --progress [-r] <directory or file source> < directory or file destination>
```

# VIM

## IP grep
```sh
[0-9]*\.[0-9]*\.[0-9]*\.[0-9]*

