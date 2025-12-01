Hashcat uses the following basic Syntax: $ hashcat -m <hash_type> -a <attact_mode> hashfile wordlist

*-m <hash_type>* specifies the hash-type in numeric format. For example, -m 1000 is for NTLM. Check the official documentation (man hashcat) and example page to find the hash type code to use.
*-a <attack_mode>* specifies the attack-mode. For example, -a 0 is for straight, i.e., trying one password from the wordlist after the other.
*hashfile* is the file containing the hash you want to crack.
*wordlist* is the security word list you want to use in your attack.