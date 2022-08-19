## How regular expressions works in JavaScript(regex)

### What are Regular Expressions or regex in JavaScript?

**Regular expressions are patterns used to match character combinations in strings.**

### What do Regular Expressions allow you to do?

**Regular expressions are used with the regex methods test() and exec() and it allow you to do  match() , replace() , search() , and split() 
.** 

### Syntax of regex in JS

```
/pattern/flags
```


### Flags in Regular Expressions 

A regular expression in JS consists of 6 flags: i, g, m, u, s, y. Without flags, the search by a regex is the same as a substring search. 


- i:- Ignore Casing mode ( the search is case-insensitive: no difference between A and a )

- g:- global mode (Makes the expression search for all occurrences)

- m:- Multiline mode (Makes the boundary characters ^ and $ match the beginning and end of every single line instead of the beginning and end of the whole string.)

- s:- Dot All mode (Makes a wild character . matches newlines as well.)

- u:- Unicode mode (Makes the expression assume individual characters as code points, not code units, and thus match 32-bit characters as well.)

- y:- Sticky mode (searching at the exact position in the text)


### How to add these flags to a regex?

forward slashes //, flags come after the second slash. 
In general notation we can express this as follows:

```
> /pattern/flags
```

## Let’s look at the example below of Regular Expressions 

### 1. It means to match one e or more than one e.

```
> /e+/g
```

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1654094664650/Xa3XVQBjb.png align="left")

### 2. It means to match one e or more than one e and follow-up a and a is optional.

```
> /e+a?/g
```

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1654093098986/cEL-szYDm.png align="left")

### 3. * is a combination of? and +, So it works the same as above.

```
> /ea*/g
```

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1654093358030/MRhz-Oa_z.png align="left")

### 4. It means to match any letter to the sentence.

```
> /\w/g
```

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1654093630499/7la2TfpSa.png align="left")

### 5. It means to match any form of white space.

```
> /\s/g
```

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1654093717911/hPdEDmIiB.png align="left")

### 6. It means to match anything that is not a white space.

```
> /\S/g
```


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1654093840301/yu-10HWyP.png align="left")

### 7. It means to match anything that is not a letter in a sentence.

```
> /\W/g
```


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1654093974836/xt0TrX06K.png align="left")

### 8. It means to match any set of characters whose length is between 6 and 7.

```
> /\w{6,7}/g
```

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1654094421483/UydLmv-C1.png align="left")

### 9. It means to match any character specified in the bracket[].

```
> /[shubham]/g
```

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1654094562656/lUjoyi7Nl.png align="left")


