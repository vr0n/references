# Shell/GNU tool command references

## csplit
```sh
# split a file at a particular line
# --digits: number of digits at end of new file (i.e., out00 versus out000)
# --quiet: supress output
# --prefix: output file name prefix (i.e, out00 versus file00)
csplit --digits=2 --quiet --prefix=out <file> "/<character sequence/" "{*}"
```
