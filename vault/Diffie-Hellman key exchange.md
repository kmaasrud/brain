**Diffie-Hellman key exchange** is a method of exchanging cryptographic keys through a public domain, with no prior shared knowledge between the client and the server. In fact, the two parts are actually not sharing keys, but creating one together.

The standard Diffie-Hellman works as follows:

- Alice and Bob agree on a shared set of numbers: The prime number $p$ and the generator $g$ which is a [[Primitive root modulo n|primitive root modulo $p$]]. The size of $p$ determines the security of the key exchange, and is thus preferrably large.
- Alice generates a random number $a$ and keeps it secretly stored on her computer. She uses this number to generate $A = g^a\mod p$, which she then shares with Bob.
- Bob also generates a random number $b$, and shares the number $B = g^b \mod p$ with Alice.
- Both repeat the same proceedure, but replace the generator $g$ with the number they recieved. So for Alice, thats $B^a \mod p$ and for Bob thats $A^b\mod p$.
- The resulting number is used as the final shared cryptographic key.

This process works because modulo exponents behave in the following way:

$$(g^a \mod p)^b \mod p = g^{ab} \mod p$$

$$(g^b \mod p)^a \mod p = g^{ba} \mod p$$

Meaning Alice and Bob end up with the same number. Note also that the only numbers that are visible to the public domain are $p$, $g$, $A$ and $B$ - none of which a malicious actor could use to get the final key (at least not without brute forcing it, which is why $p$ needs to be large).