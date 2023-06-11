# CerealSpiller Keylogger

CerealSpiller is a simple keylogger script written in Python. It captures keystrokes entered by the user and stores them in a file. The script also provides basic encryption functionality to encrypt the captured keystrokes.

## Features

- **Keystroke Logging**: The script captures keystrokes, including normal characters, special keys (e.g., Space, Enter, Backspace), and Ctrl + C, and logs them to a file.
- **File Encryption**: The captured keystrokes can be encrypted using the Fernet encryption scheme provided by the cryptography library.
- **Graceful Termination**: The script can be terminated by pressing the Escape key, which closes the file, encrypts the captured keystrokes, and exits the program.

## Requirements

- Python 3.x
- Install dependencies by running `pip install -r requirements.txt`

## Usage

1. Run the script by executing the following command: `python CerealSpiller.py`.
2. The script will start capturing keystrokes and logging them to a file named `secretlogs_<date>.txt`, where `<date>` is the current date in the format `YYYY-MM-DD`.
3. Press the Escape key to stop the keylogging and encrypt the captured keystrokes.
4. The encrypted file will be saved as `secretlogs_<date>.txt.encrypted`.

## Functionality

### Keystroke Logging

CerealSpiller captures various types of keystrokes, including:

- Normal characters: Any letter, number, or symbol entered by the user.
- Special keys: Space, Enter, Backspace.
- Ctrl + C: Captures the Ctrl + C combination, which is commonly used for copying text.

### File Encryption

CerealSpiller provides a basic encryption functionality using the Fernet encryption scheme from the cryptography library. When the keylogging is stopped, the captured keystrokes are encrypted using a provided password and saved to an encrypted file. This ensures that the captured data remains secure and unreadable without the encryption key.

### Graceful Termination

The keylogging process can be terminated gracefully by pressing the Escape key. When the Escape key is pressed, CerealSpiller performs the following actions:

1. Closes the file used for logging keystrokes.
2. Encrypts the captured keystrokes using the provided password.
3. Exits the program.



ddddddddddddd

# File Decryption Script

This script allows you to decrypt an encrypted file using the Fernet encryption scheme from the cryptography library in Python.
Prerequisites

##Before running the script, make sure you have the following:

    Python 3 installed
    The cryptography library installed. You can install it using pip:

    pip install cryptography

#Usage

To use this script, follow these steps:

    Copy the script into a Python file (e.g., decrypt_file.py).

    Import the Fernet class from the cryptography.fernet module:

    python

###from cryptography.fernet import Fernet

Run the script with the following command:

python decrypt_file.py <encrypted_file_path> <fernet_key>

Replace <encrypted_file_path> with the path to the encrypted file you want to decrypt, and <fernet_key> with the encryption key used for encryption.

For example:

shell

    python decrypt_file.py encrypted_file.txt.encrypted my-fernet-key

Script

python

from cryptography.fernet import Fernet
import sys

def decrypt_file(encrypted_file_path, key):
    # Read the encrypted file content
    with open(encrypted_file_path, "rb") as encrypted_file:
        encrypted_content = encrypted_file.read()

    # Create a Fernet cipher object with the provided key
    cipher = Fernet(key)

    try:
        # Decrypt the encrypted content
        decrypted_content = cipher.decrypt(encrypted_content)

        # Get the original file path (without the ".encrypted" extension)
        original_file_path = encrypted_file_path[:-10]

        # Write the decrypted content back to the original file
        with open(original_file_path, "wb") as original_file:
            original_file.write(decrypted_content)

        print(f"File decrypted and saved as: {original_file_path}")
    except Exception as e:
        print("Error occurred during decryption:", e)

if __name__ == "__main__":
    if len(sys.argv) < 3:
        print("Usage: python decrypt_file.py <encrypted_file_path> <fernet_key>")
        sys.exit(1)

    encrypted_file_path = sys.argv[1]
    key = sys.argv[2].encode()

    decrypt_file(encrypted_file_path, key)

Please note that you need to replace <encrypted_file_path> and <fernet_key> with the actual values when running the script.

