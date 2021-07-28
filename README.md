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

# send a cookie with a curl request
# -b cookie in "cookie=value" format
curl -b "cookie=value" example.com/anywhere
```

## date
```sh
# Do math on a date in YYYY-MM-DDT:H:M:SZ format (any other format works as well)
# -u return time in UTC (optional, obviously)
# -d display time based on this date modifier (1 minute from now, i.t.e.)
date -u +"%Y-%m-%dT%H:%M:%SZ" -d "+1 minute"
```

## find
```sh
# search all while excluding one dir (exclude /proc, i.t.e.)
# / start at root directory
# -path select a path
# /proc is the path
# -prune exclude previously called path from search
find / -path /proc -prune
```

## join
```sh
# Had a really parochial problem where I had two files that contained different email headers/
# I wanted to create a new file that both sets of email headers from each file in their own
# column, but I also wanted them to be in alphabetical order and to be on the same line if there
# was a match across both files (for example, the new file should contain "To:|To:" as one line
# because both files included a "To:" header, but if only of the fiels contained that header, I
# would want the line to read "To:|" or "|To:" depending on which file did not include the header.
#
# To solve this problem, I utilized the `join` command for the first time like so:
# -o Output format (syntax of <filenum>.<columnnum>). Each file only had one "column"
# -t Delimeter between info from the first file and second file (a single space by default)
# -a Print unpaired lines from either file 1 or file 2 (in this example, I print unpaired from both)
# --nocheck-order I saw weird behavior when I didn't include this line, and everything worked when added
join -o "1.1,2.1" -t '|' -a 1 -a 2 --nocheck-order <first file> <second file>
```

## nc
```sh
# Check for open ports if you can't get to Nmap
# -z check if you can connect and do nothing else
# -v verbose output
for i in {0..65535}; do nc -z -v <IP> $i 2>&1 | grep -i connected; done
```

## rsync
```sh
# --progress should just be aliased in rsync, as it is awesome
# -r to recursively copy files if copying a directory
# if copying a directory, a trailing slash will copy the directories contents in full. No trailing slash will just copy the directory and its contents
rsync --progress [-r] <directory or file source> <directory or file destination>
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
# Just an example of how regex works in Vim
# Search this way after using '/'
[0-9]*\.[0-9]*\.[0-9]*\.[0-9]*
```

## Case Insensitive search
```sh
# Just add \c anywhere in the / call
/search case insensitive\c
```

## Remove duplicate lines
```sh
:sort u
```
