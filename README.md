# Vigenère Cipher Python Implementation - Documentation

## Overview

This Python module implements the Vigenère Cipher, a polyalphabetic substitution cipher used for encrypting and decrypting messages. The Vigenère Cipher improves upon the simple Caesar Cipher by using a keyword to perform encryption and decryption, making it more secure and versatile.

This module provides two main functions, `vigenere_encrypt()` and `vigenere_decrypt()`, which handle the encryption and decryption processes, respectively.

## Functions

### `vigenere_encrypt(plaintext, keyword)`

Encrypts a given plaintext using the Vigenère Cipher algorithm.

**Parameters:**

- `plaintext` (str): The message to be encrypted.
- `keyword` (str): The keyword used for encryption. The keyword is case-insensitive; it can include spaces.

**Returns:**

- `str`: The encrypted ciphertext.

**Example:**

```python
>>> vigenere_encrypt("Hello World", "KEY")
'RIJVSUYVJN'
```

### `vigenere_decrypt(ciphertext, keyword)`

Decrypts a given ciphertext using the Vigenère Cipher algorithm.

**Parameters:**

- `ciphertext` (str): The encrypted message to be decrypted.
- `keyword` (str): The keyword used for decryption. The keyword is case-insensitive; it can include spaces.

**Returns:**

- `str`: The decrypted plaintext.

**Example:**

```python
>>> vigenere_decrypt("RIJVSUYVJN", "KEY")
'HELLOWORLD'
```

## Algorithm

Both encryption and decryption processes in the Vigenère Cipher involve a similar algorithm:

1. Convert the keyword to uppercase for case-insensitivity.
2. Determine the length of the keyword.
3. Iterate through each character in the plaintext (for encryption) or ciphertext (for decryption).
4. For each alphabet letter, find the corresponding shift value based on the letter's position in the repeating keyword.
5. Adjust the base value based on whether the letter is lowercase or uppercase in the original message.
6. Encrypt (for encryption) or decrypt (for decryption) the letter using the Vigenère Cipher algorithm, applying the shift.
7. Append the encrypted or decrypted letter to the result string.

Non-alphabet characters (such as spaces or punctuation) are left unchanged in both processes.

## Usage

To use this module in your Python code, import the `vigenere_encrypt()` and `vigenere_decrypt()` functions and call them with appropriate arguments.

```python
from vigenere_cipher import vigenere_encrypt, vigenere_decrypt

# Example 1: Encrypting a message
plaintext = "Hello World"
keyword = "KEY"
encrypted_message = vigenere_encrypt(plaintext, keyword)
print("Encrypted message:", encrypted_message)  # Output: 'RIJVSUYVJN'

# Example 2: Decrypting a message
ciphertext = "RIJVSUYVJN"
decrypted_message = vigenere_decrypt(ciphertext, keyword)
print("Decrypted message:", decrypted_message)  # Output: 'HELLOWORLD'
```
