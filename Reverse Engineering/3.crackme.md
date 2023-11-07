# Crackme-py
Crackme-py <br>
Link : https://mercury.picoctf.net/static/f440bf2510a28914afae2947749f2db0/crackme.py <br>
**Identifikasi:** <br>
Kita diberi sebuah file Python dan jika kita melakukan RUN pada file Python tersebut adalah : <br>
>What's your first number? 1 <br>
>What's your second number? 2 <br>
>The number with largest positive magnitude is 2 <br>

Kita dapat mengetahui bahwa berapapun angka yang kita berikan untuk perintah tersebut kita tidak akan mendapatkan FLAG.
Maka dari itu kita akan masuk ke dalam file tersebut untuk mendapatkan informasi lebih lanjut.

    # Hiding this really important number in an obscure piece of code is brilliant!
    # AND it's encrypted!
    # We want our biggest client to know his information is safe with us.
    bezos_cc_secret = "A:4@r%uL`M-^M0c0AbcM-MFE0g4dd`_cgN"

    # Reference alphabet
    alphabet = "!\"#$%&'()*+,-./0123456789:;<=>?@ABCDEFGHIJKLMNOPQRSTUVWXYZ"+ \
            "[\\]^_`abcdefghijklmnopqrstuvwxyz{|}~"



    def decode_secret(secret):
    """ROT47 decode

    NOTE: encode and decode are the same operation in the ROT cipher family.
    """

    # Encryption key
    rotate_const = 47

    # Storage for decoded secret
    decoded = ""

    # decode loop
    for c in secret:
        index = alphabet.find(c)
        original_index = (index + rotate_const) % len(alphabet)
        decoded = decoded + alphabet[original_index]

    print(decoded)



    def choose_greatest():
    """Echo the largest of the two numbers given by the user to the program

    Warning: this function was written quickly and needs proper error handling
    """

    user_value_1 = input("What's your first number? ")
    user_value_2 = input("What's your second number? ")
    greatest_value = user_value_1 # need a value to return if 1 & 2 are equal

    if user_value_1 > user_value_2:
        greatest_value = user_value_1
    elif user_value_1 < user_value_2:
        greatest_value = user_value_2

    print( "The number with largest positive magnitude is "
        + str(greatest_value) )



    choose_greatest()
Pada file Python diatas kita mendapatkan sebuah code enkripsi <br> 
>A:4@r%uL`M-^M0c0AbcM-MFE0g4dd`_cgN

pada bagian "bezoz_cc_seceret" <br>
Dan juga terdapat informasi bahwa kode tersebut menggunakan enkripsi ROT-47.
 
**Penyelesaian:**
![image](https://github.com/NeloRedgrave/WriteUp_CTF/assets/140806028/46308513-55f8-4e0e-852b-13918bf22645)

