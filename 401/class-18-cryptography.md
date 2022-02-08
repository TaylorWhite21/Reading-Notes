# Cryptography

## Ceaser Cipher

The Caesar Cipher is a simple substitution cipher which replaces each original letter with a different letter in the alphabet by shifting the alphabet by a certain amount.
Using a shift of 6, an ceaser cipher would look like:  
A	B	C	D	E	F	G	H	I	J	K	L	M	N	O	P	Q	R	S	T	U	V	W	X	Y	Z  
G	H	I	J	K	L	M	N	O	P	Q	R	S	T	U	V	W	X	Y	Z	A	B	C	D	E	F

The word Secret would Become:
```
S	E	C	R	E	T
Y	K	I	X	K	Z
```
## Cracking a cipher
There are 3 techniques that can be used to crack a cipher:
1. Frequency Analysis
  - Human languages tend to use some letters more than others. For example, "E" is the most popular letter in the English language. We can analyze the frequency of the characters in the message and identify the most likely "E" and narrow down the possible shift amounts based on that.
2. Known Plaintext
  - Another term for the original unencrypted message is plaintext. If the enemy already knew some part of the plaintext, it will be easier for them to crack the rest of the encrypted version.
3. Brute Force
  - There are only 25 possible shifts because a shift of 0 or 26 would keep it the same. The enemy could take some time to try out each of them and find one that yielded a sensible message. They wouldn't even need to try the shifts on the entire message, just the first word or two.
