# Shell/GNU tool command references

## csplit
```sh
# split a file at a particular line
# --digits: number of digits at end of new file (i.e., out00 versus out000)
# --quiet: supress output
# --prefix: output file name prefix (i.e, out00 versus file00)
csplit --digits=2 --quiet --prefix=out <file> "/<character sequence>/" "{*}"
```

## curl
```sh
# send post request with form data
# -d is the data
curl -d "field0=value0&field1=value1" example.com/form
```
```sh
# send a cookie with a curl request
# -b cookie in "cookie=value" format
curl -b "cookie=value" example.com/anywhere
```
## date
```sh
# Do math on a date in YYYY-MM-DDT:H:M:SZ format (any other format works as well)
date -u +"%Y-%m-%dT%H:%M:%SZ" -d "+1 minute"
```

## find
```sh
# search all while excluding one dir (proc, i.t.e.)
# -path select a path
# /prune is the path
# -prune exclude previously called path from search
find / -path /proc -prune
```

## nc
```sh
# Check for open ports if you can't get to Nmap
for i in {0..65535}; do nc -z -v <IP> $i 2>&1 | grep -i connected; done
```

## rsync
```sh
# --progress should just be aliased in rsync, as it is awesome
# -r to recursively copy files if copying a directory
# if copying a directory, a trailing slash will copy the directories contents in full. No trailing slash will just copy the directory and its contents
rsync --progress [-r] <directory or file source> < directory or file destination>
```

## sort
```sh
# I spent **years** adding "| sort | uniq" to the end of commands. 
# Turns out you can just...
sort -u
```

# VIM

## IP grep
```sh
[0-9]*\.[0-9]*\.[0-9]*\.[0-9]*

## Case Insensitive search
# just add \c anywhere in the / call
```sh
/search case insensitive\c
```
