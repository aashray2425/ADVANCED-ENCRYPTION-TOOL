# ADVANCED-ENCRYPTION-TOOL

COMPANY: CODTECh IT SOLUTIONS

NAME: Aashray Premkumar Dhone

INTERN ID: CODHC173

DOMAIN: Cyber Security & Ethical Hacking

BATCH DURATION: January 30th, 2025 to March 2nd, 2025

MENTOR NAME: Neela Santhosh Kumar

Overview This AES encryption tool provides encryption and decryption functionalities using AES with key sizes of 128, 192, or 256 bits. The tool operates in ECB mode and allows users to securely encrypt and decrypt files using a hexadecimal key.

Features Supports AES key sizes of 128-bit, 192-bit, and 256-bit.

Encrypts and decrypts files using AES in ECB mode.

Command-line interface with options for input files, output files, and encryption keys.

Implements padding for proper AES block alignment.

Generates secure random 256-bit keys.

Output : ![Screenshot 2025-01-30 153331](https://github.com/user-attachments/assets/54135047-965b-47a7-864d-c1e94086c373)

![Screenshot 2025-01-30 153534](https://github.com/user-attachments/assets/f75038e3-ab3b-4dce-afc9-eaf37b0f262a)

![Screenshot 2025-01-30 154031](https://github.com/user-attachments/assets/922bf37b-d546-4982-b090-8ca698105acc)


Installation Ensure you have Python installed on your system. This script does not require additional dependencies beyond Python's standard library.

Key Generation

To generate a 256-bit secure random key, use the following script:

import secrets

key = secrets.token_hex(32)

print(key) print(len(key))

This will output a 64-character hexadecimal key that can be used for AES encryption.

Example Output: a3f8b4e93c1f2d5a8b9e3d7c6a4f1b2d5e8c7f0a9d3b2c1e4f5a6b7c8d9e0f1a 64

Usage Run the script with the following command-line arguments:

Encrypt a file

python aes_tool.py -e <input_file> -o <output_file> -k <hexadecimal_key>

-e or --encrypt : Path to the file you want to encrypt.

-o or --output : Path to save the encrypted output.

-k or --key : Hexadecimal key of length 32 (128-bit), 48 (192-bit), or 64 (256-bit).

Decrypt a file

python aes_tool.py -d <input_file> -o <output_file> -k <hexadecimal_key>

-d or --decrypt : Path to the file you want to decrypt.

-o or --output : Path to save the decrypted output.

-k or --key : Hexadecimal key used for encryption.

Example Encryption:

python aes_tool.py -e plaintext.txt -o encrypted.bin -k 0123456789abcdef0123456789abcdef

Decryption: python aes_tool.py -d encrypted.bin -o decrypted.txt -k 0123456789abcdef0123456789abcdef

Error Handling If an incorrect or missing argument is provided, the script will display an error message and exit.

The key must be in hexadecimal format and match the required length (32, 48, or 64 characters).

How It Works Padding: Ensures the plaintext is a multiple of 16 bytes before encryption.

Key Expansion: Generates round keys from the provided key.

Encryption Process: SubBytes

ShiftRows

MixColumns

AddRoundKey

Decryption Process:

Inverse AddRoundKey

Inverse MixColumns

Inverse ShiftRows

Inverse SubBytes

Unpadding: Removes extra bytes added during encryption.

Performance The execution time for encryption and decryption is measured using time.thread_time() and displayed upon completion.
