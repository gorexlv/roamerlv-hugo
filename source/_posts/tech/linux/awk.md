---
title: AWK Basic
tags: [linux]
categories: [tech]
---

## Basic Structure

AWK is line oriented, the essential organization of an AWK program like this:

```bash
awk 'pattern1{action1} pattern2{action2}' filename
```

The pattern specifier would be 'blank' or 'BEGIN' or 'END' or '**statement**'

## Dynamic Variables

You can pass a variable to the insides of an AWK script

## Arithmetic Expressions

| Operator | Type | Meaning |
| --| --|--|
| + | Arithmetic | Addition |
| - | 

``` sh
#!/bin/awk -f
BEGIN {
    # Print the squares from 1 to 10 the first way
    i=1;
    while (i <= 10) {
        printf "The square of ", i, " is ", i*i;
        i = i+1;
    }

    # do it again, using more concise code
    for (i=1; i <= 10; i++) {
        printf "The square of ", i, " is ", i*i;
    }

    # now end
    exit;
}
```

``` sh
#!/bin/awk -f
BEGIN {
    print "type a number";
}
{
    print "The square of ", $1, " is ", $1*$1;
    print "type another number";
}
END {
    print "Done"
}
```

``` sh
#!/bin/awk -f
BEGIN {
    # How many lines
    lines=0;
    total=0;
}
{
    # this code is executed once for each line
    # increase the number of files
    lines++;
    # increase the total size, which is field #1
    total+=$1;
}
END {
    # end, now output the total
    print lines " lines read";
    print "total is ", total;
    if (lines > 0 ) {
        print "average is ", total/lines;
    } else {
        print "average is 0";
    }
}
```







