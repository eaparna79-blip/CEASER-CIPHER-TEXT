[caesar cipher text.py](https://github.com/user-attachments/files/28156910/caesar.cipher.text.py)

alphabets=['a','b','c','d','e','f','g','h','i','k','l','m','n','o','p','q','r','s','t','u','v','w','x','y','z']
def encryption(plain_text,shift_key):
    cipher_text=""
    for letter in plain_text:
        if letter in alphabets:
            position=alphabets.index(letter)
            new_position=(position+shift_key)%26
            cipher_text+=alphabets[new_position]
        else:
            cipher_text+=letter
    print(f"here's the text after encryption: {cipher_text}")

def decryption(cipher_text,shift_key):
    for letter in cipher_text:
        if letter in alphabets:
            position=alphabets.index(letter)
            new_position=(position-shift_key)%26
            plain_text+=alphabets[new_position]
        else:
            plain_text+=letter
    print(f"here 's the text after decryption: {plain_text}")

wanna_end=False
while not wanna_end:
    what_to_do=input("type 'encrypt' for encryption and 'decrypt' for decryption:")
    text=input("type your message:")
    key=int(input("enter the shift key:"))
    if what_to_do=="encrypt":
        encryption(plain_text=text,shift_key=key)
    elif what_to_do=="decrypt":
        decryption(cipher_text=text,shift_key=key)

    play_again=input("type 'yes' to continue and type 'no' to exit:")
    if play_again=="no":
        wanna_end=True
        print("have a nice day!!bye...")
        
