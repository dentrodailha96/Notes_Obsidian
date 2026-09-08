![[Pasted image 20260522101613.png]]

### Looping

- If I want to loop in a sequence of files and return the cat based that these files starts with the same name and have different tail. 

```
for i in {1..8} ; do cat prefix_${i}; done
 
```


### Grep
Get an information from  a row:
	A > After n lines
	B  > Before n lines 

Example:
```
grep 'L337' -A5 -B1 vehicles
```
Is possible to use it in multiple files from a directory:

```
 grep “string*” *
```

### Specific row Ubuntu

-  `awk` is a text-processing tool that reads a file **line by line** and applies rules to each line. Think of it as a mini-programming language built for working with structured text.

```
`awk 'condition { action }' file`
```

