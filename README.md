This is a **Multi Pad Attacker**, a solution for programming assignment-1 of Cryptography-I course by Stanford University on Coursera.

The system aims to show how using the same key for one time pad encryption, making it "multi pad", compromises the security of the communication. Assuming we have a few ciphertexts and a target ciphertext which we want to decode, all encrypted using the same key (ciphertext = message xor key), we can find the key and use it to decode all the messages.

The system has two workings:
1. User inputs ciphertexts and target ciphertext
2. Using default ciphertexts and target ciphertext stored in the system

**High-level working of the system:**
* Using the ciphertexts and target ciphertext, the target message is decoded and displayed. 
* An option is provided to make corrections to the decoded target message if any mistake is found. 
* Using the final target message, key is calculated and is used to decode the other ciphertexts.
* From the other decoded messages, we can confirm if the target message is correct. 
* If its wrong, we can correct the target message again until we are satisfied with the decryption.

**Working of target message decoding:**
* While XORing two ciphertexts, alphabets appear in the result only if an alphabet is XORed with space.
  * lower-case alphabet xor space = upper-case alphabet
  * upper-case alphabet xor space = lower-case alphabet
* We use the alphabets in the results of XOR to guess the target message.
* If the result has an alphabet at a specific position for majority of the ciphertexts, the target message probably has a space at that position.
* If the result has non-alpha character at a specific position for majority of the ciphertexts, the ciphertexts probably have a space at that position and the target message has the maximum occured character in reversed case.
