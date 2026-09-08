Scenario SadServers: https://sadservers.com/scenario/minneapolis

1) Count the rows amount in the file: 
wc {path/file}

![[Pasted image 20260722095844.png]]

**2801**: Number of rows/lines in a file. **3084**: Number of words in a file. **268957**: Size of the file in bytes. **data.csv**: Name of the file

2) Split the file into the amount of rows in each file.
Example: we want 10 files, so each file with 281 rows. 

- But we want to keep the header in each file. So we must follow this stack: https://stackoverflow.com/questions/51420966/split-csv-files-into-smaller-files-but-keeping-the-headers

- We want an specific name for each file.

Losung: 
```bash
awk -v l=281 -v name="data" '(NR==1){header=$0;next}
                (NR%l==2) {
                   close(file);
                   file=sprintf("%s-%0.2d.csv",name,c++);
                   print header > file
                }
                {print > file}' data.csv
```

- `name="data"` — pass in the string prefix as a variable so you can reuse the script for other names without editing it.
- `file=sprintf("%s-%d.csv", name, c++)` — builds `data-0.csv`, `data-1.csv`, etc. Using `c++` (post-increment) instead of `++c` makes the first file start at `0` instead of `1`.
- Removed the zero-padding (`%0.5d` → `%d`) since your example (`data-0.csv`, `data-1.csv`) doesn't use padding. If you actually want padded numbers (`data-00.csv`, `data-01.csv`), use `%0.2d` (or however many digits) instead of `%d`.

3) If we want a specific size for each file we must follow this  tutorial: https://www.geeksforgeeks.org/linux-unix/split-command-in-linux-with-examples/

```bash
awk -v maxsize=25000 -v name="data" '(NR==1){header=$0; hlen=length(header)+1; next}
{ 
	if (file == "" || size + length($0) + 1 > maxsize) { 
		close(file); 
		file=sprintf("%s-%0.2d.csv", name, c++); 
		print header > file 
		size = hlen 
	} 
	print > file 
	size += length($0) + 1 
}' data.csv
```

- size = hlen: _Reset the byte counter — right now, this new file already contains just the header, so start counting from the header's size, not from zero."_ This matters because every split file gets the header repeated at the top (so each chunk is still a valid, readable CSV on its own), and that header takes up real space too — it needs to count toward the 32K limit, or you could go over.
-  size += length($0) + 1 : This runs **every time a data line is written** to the current file. `$0` is the current line (the whole row), so `length($0)` is how many bytes that line takes up, and `+1` again accounts for the newline character at the end of the line.
- if (file == "" || size + length($0) + 1 > maxsize) : uses this running `size` to ask, before writing the next line: _"If I add this line to the current file, will it go over 32000 bytes?"_ If yes, it closes the current file and starts a new one (with the header again, resetting `size` back to `hlen`). If no, it just writes the line and updates `size` to reflect the new total.

Verify the file sizes:

`ls -lh *.csv`

