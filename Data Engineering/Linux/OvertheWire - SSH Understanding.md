 ## Level 0 - How to connect to a server

![[Pasted image 20250525194251.png]]

 - <user>@<server> -p <port> then we added the password of the user. 

## Level 1 
- cat: open a file
- copy: ctrl + shift + c
- paste: ctrl + shit + v

	- If the file is called "-" to open it we must use: "cat <-" or "cat ./-" 
(https://medium.com/@.Qubit/how-to-create-open-find-remove-dashed-filename-in-linux-27ee297d1740)

## Level 2
	- to read files with spaces in the name we must but the name of the file between 'file name'

## Level 3:
	- to open all the files of a directory: ls -a 

## Level 4:
	 - command du shows the size of every subdirectory inside of a directory. 
	 - du -h: shows all the human readable format files
obs.: To open a file inside a directory, that is inside another directory you must define the 'directory/filename'.

## Level 5: 
	- to get the detailed information from files in a directory you must use: ls -lh (detail and human executable)
	- use: find . -maxdepth x -type f  ! executable -ls 
- find is to find 
- .-maxdepth x : how deep you would like to look up into the directories
- -type f: restrict only to regular files
- ! : not 
- -executable : type of the files
- -ls: where to find 

## Level 6:
	It's possible to find a file by the size, user and group in the server. The command below makes this possible: 
	
	find / -type f -size 33c -user bandit7 -group bandit6

find: to find something
/: look from the root
-type f: restrict only to regular files
-size 33c: define the size and add the c after the number to restrict to that size. 
-user: define the user after it 
-group: define the group after group

## Level 7: 
	- show the currently directory path: pwd 
	- to find a string in files inside a directory:
	grep -rnw 'directory path' -e '<string>'
grep: command plaintext data set for lines that match a regular expression
-rnw: recursive, line number, whole world
-e: pattern used to search

## Level 8: 
	In order to find a string that repeats in a file we must use the command "sort". 

	sort <file.txt> | uniq -u (this case shows only the unique strings)
	sort <file.txt> | uniq -c (this case shows the strings and how many times they repeat)

## Level 9
	To find a string inside a document:
		strings {document name.type} | grep -A1 '{string}'

		strings = extracts printable strings from the file
		grep = a expression to helps search for a specific text within files
		A1 = number the lines after it you would line to show

## Level 10 
	 Base64 = binary-to-text encoding scheme that represents binary data in ASCII string format by translating into a radix-64 representation. AKA, Some systems (like email or web URLs) don't work well with raw binary data (like images or files). Base64 converts that data into plain text that can safely be sent or stored.

	  cat {document} | base64 --decode

	cat = read document
	| = action after it
	base64 = code to be decoded
	 --decode = to decode the code

## Level 11
	ROT13 - is a simple letter substitution cipher used to obsure text. (Tipo ZENIT POLAR).

	tr 'A-Za-z' 'N-ZA-Mn-za-m'

	tr = translating or deleting character in linux
	the following sequence is the translation from ROT13.

## Level 12

	Hexdump = hexdump is a command that show the contet of a file in hexadecimal format (base 16). When a file does not contain a text data, like images and compiled programs, so you can see the raw bytes.

	How to decode: https://mayadevbe.me/posts/overthewire/bandit/level13/

## Level 13

	SSH is a connection from your private computer to a server. The server create a special encripted string, then the ssh connection is the prove that you can decript this string. 

	sshkey = types of password

- private key = super secret 
	zB.: .pem file 
- public key - public (can be everywhere)



