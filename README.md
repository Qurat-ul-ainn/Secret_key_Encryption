# Secret_key_Encryption

Instruction: https://seedsecuritylabs.org/Labs_16.04/PDF/Crypto_Encryption.pdf


###Task 1


Step 1: Use the text of the Gettysburg Address as the original article file gettysburg.txt. The usage of tr is available in GNU documentations. -d means 'delete' and -cd means 'delete the complement of', so first we just keep the letters, spaces, and newlines as the plaintext.

$tr [:upper:] [:lower:] < gettysburg.txt > lowercase.txt
$tr -cd '[a-z][\n][:space:]' < lowercase.txt > plaintext.txt


Step 2: Use Python console to generate a permutation of a-z:

>>> import random
>>> s = "abcdefghijklmnopqrstuvwxyz"
>>> ''.join(random.sample(s,len(s)))


'azfgmunhrqwetlxicdksjbpvyo'


Step 3: Encryption

$tr "abcdefghijklmnopqrstuvwxyz" "azfgmunhrqwetlxicdksjbpvyo" < plaintext.txt > ciphertext.txt

###Break
   
   Use http://www.richkni.co.uk/php/crypta/freq.php to analyze the frequency of ciphertext.txt, its full report shows as analysis.md.

By single letter frequcey,the letters in ciphertext sorted by frequency are:

msaxhdlrgkefpnubjiztywcqvo 
Compared with letter frequency rank as eothasinrdluymwfgcbpkvjqxz in modern English (see Wikipedia)

$ tr 'msaxhdlrgkefpnubjiztywcqvo' 'eothasinrdluymwfgcbpkvjqxz' < ciphertext.txt > out1.txt

###Task 2
   
 Ref to the manual of enc.
 
 Cipher Block Chaining (CBC)
 
 Each block of plaintext is XORed with the previous cipher block.
   
   


