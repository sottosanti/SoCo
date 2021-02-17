# Log Analysis

cat access.log | cut -d “ “ -f 1 | sort | uniq -c | wc -l
Cat to print
Cut to remove sections from each line of files
	-d is a delimiter (b for byes -c for chars)
Sort sorts lines of text
Uniq is report or omit certain lines
	-c is count
wc is print newline, word, and byte counts for each file
	-l is print the number of unique lines

cat access.log | cut -d ‘”’ -f3 | cut -d ‘ ‘ -f2 | sort | uniq -c | sort -rn
	(‘ “ ‘)
	-f is fields
n is numeric sort
r is reverse
sort before using uniq -c 

awk -F“ “ ‘{print $6}’ access.log | sort | uniq -c
awk is pattern scanning and proccesing language

Log one:
cat squid_access.log | awk ‘{print $2}’ | sort -n
Got times

cat squid_access.log | awk ‘{print $3}’ | sort | uniq -c | sort -rncd
