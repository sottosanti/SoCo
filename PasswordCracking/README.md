# Password Cracking

For pokemon one: <br>
Get long list of pokemon names <br> 
Create hash.txt for uncracked passwords (md5 sums) <br>
hashcat -m 0 -a 0 ./hash.txt pokenames.txt <br>

Windows one: <br>
21259DD63B980471AAD3B435B51404EE:1E43E37B818AB5EDB066EB58CCDC1823 <br>
Copied into https://crackstation.net/ <br>
NTLM hashes (older is called LM) <br>
https://ophcrack.sourceforge.io/download.php?type=ophcrack <br>
https://ophcrack.sourceforge.io/tables.php <br>
Dowloaded rainbow tables <br>
Echo’d all uncracked passwords from challenge into hashes.txt <br>
ophcrack -d . -t . -n 4 -s hashes.txt <br>
<br>
Law and Order: <br>
Gather trancript of words from all episodes <br>
-hashcat hash.txt -m 0 -a 6 hash.txt svu.txt ?d?d <br>
0 = straight (dict) <br>
1 = combination <br>
3 = brute force <br>
6 = hybrid word list + mask <br>
7 = hybrid mask + word list <br>
 
Wordlist               |   $P$   | hashcat -a 0 -m 400 example400.hash example.dict <br>
 Wordlist + Rules | MD5   | hashcat -a 0 -m 0 example0.hash example.dict -r rules/best64.rule <br>
 Brute-Force         | MD5   | hashcat -a 3 -m 0 example0.hash ?a?a?a?a?a?a <br>
 Combinator         | MD5   | hashcat -a 1 -m 0 example0.hash example.dict example.dict <br>
