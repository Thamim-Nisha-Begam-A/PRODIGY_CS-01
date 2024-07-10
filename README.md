
def caesar_cipher(text, shift, mode):
    result = ""
    for char in text:
        if char.isalpha():
            base = ord('A') if char.isupper() else ord('a')
            shifted_char = chr((ord(char) - base + shift) % 26 + base)
            result += shifted_char
        else:
            result += char
    return result

def main():
    user_text = input("Enter the text to encrypt or decrypt: ")
    shift_value = int(input("Enter the shift value (positive for encryption, negative for decryption): "))
    operation_mode = input("Enter 'encrypt' or 'decrypt': ").lower()
    if operation_mode == "encrypt":
        encrypted_text = caesar_cipher(user_text, shift_value, mode="encrypt")
        print(f"Encrypted text: {encrypted_text}")
    elif operation_mode == "decrypt":
        decrypted_text = caesar_cipher(user_text, shift_value, mode="decrypt")
        print(f"Decrypted text: {decrypted_text}")
    else:
        print("Invalid operation mode. Please enter 'encrypt' or 'decrypt'.")

if __name__ == "__main__":
    main()
