source: https://medium.com/@ravinderhundal/linux-pipes-explained-the-smartest-way-to-chain-commands-b192d03544d3

IPC = inter-process communication that connects the standard output (stdout) of one command to the standard input (stdin) of other. In other words, seamless data flow between bash commands. 

- It's possible to find information inside documents using pipes.
### Syntax: 

command1  |  command2

### How to use:

- Filtering Output: ls -la | grep .claude
- Sorting Data: ls -la | sort -k 5 -n (sort list by the 5 column) | sort -rn (sorts results numerically, highest count first). 
- Counting Lines: cat HEAD | wc -l
- Finding Top Errors: cat server.log | grep "ERROR" | sort | uniq -c | sort -nr
- echo: print something or message.
- awk: extract the fields from a file. Example: awk '{print $1}'
- uniq -c : count the unique values in a dataset. The -c consider the unique values consecutives.
- head -n : shows the first n lines.

### Tips

- Bash scripts to catch errors in any part of pipeline: set -euo pipefail 
	- -e exit immediately on error (close the terminal)
	- -u treat unset variable as error
	- -o pipefail propagate pipe failures 

	To disable: set +o pipefail
- Use "strace" or "time"  to analyze performance bottlenecks

## Observations
 - Between git commands we don't use pipes, we use &&  (run the next command only if the previous one succeeded)

