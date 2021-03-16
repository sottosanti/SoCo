# Log Analysis

cat access.log | cut -d “ “ -f 1 | sort | uniq -c | wc -l <br>
Cat to print <br>
Cut to remove sections from each line of files <br>
	-d is a delimiter (b for byes -c for chars) <br>
Sort sorts lines of text <br>
Uniq is report or omit certain lines <br>
	-c is count <br>
wc is print newline, word, and byte counts for each file <br>
	-l is print the number of unique lines <br>
	
cat NASA_access.log | grep -E " 404 " -o | uniq -c

cat access.log | cut -d ‘”’ -f3 | cut -d ‘ ‘ -f2 | sort | uniq -c | sort -rn <br>
	(‘ “ ‘) <br>
	-f is fields <br>
n is numeric sort <br>
r is reverse <br>
sort before using uniq -c  <br>

awk -F“ “ ‘{print $6}’ access.log | sort | uniq -c <br>
awk is pattern scanning and proccesing language <br>

Log one: <br>
cat squid_access.log | awk ‘{print $2}’ | sort -n <br>
Got times <br>

cat squid_access.log | awk ‘{print $3}’ | sort | uniq -c | sort -rncd <br>
