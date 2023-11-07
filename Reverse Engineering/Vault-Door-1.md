# Vault-Door-1
Category : Reverse Engineering 
# Description
# Hint
**Identifikasi:**
Kita diberi file java dan setelah kita Jalankan maka akan disuruh untuk memasukan sebuah password. <br>
Dan karena kita tidak tahu passwordnya maka kita akan melihat isi dari file Java tersebut.<br>
Setelah melihat isi dari file tersebut maka kita pasti akan berfokus pada string ini: <br>
                                                                                                                                                                                                         
    import java.util.*;

    class VaultDoor1 {
    public static void main(String args[]) {
        VaultDoor1 vaultDoor = new VaultDoor1();
        Scanner scanner = new Scanner(System.in);
        System.out.print("Enter vault password: ");
        String userInput = scanner.next();
        String input = userInput.substring("picoCTF{".length(),userInput.length()-1);
        if (vaultDoor.checkPassword(input)) {
            System.out.println("Access granted.");
        } else {
            System.out.println("Access denied!");
        }
    }

    // I came up with a more secure way to check the password without putting
    // the password itself in the source code. I think this is going to be
    // UNHACKABLE!! I hope Dr. Evil agrees...
    //
    // -Minion #8728
    public boolean checkPassword(String password) {
        return password.length() == 32 &&
               password.charAt(0)  == 'd' &&
               password.charAt(29) == '9' &&
               password.charAt(4)  == 'r' &&
               password.charAt(2)  == '5' &&
               password.charAt(23) == 'r' &&
               password.charAt(3)  == 'c' &&
               password.charAt(17) == '4' &&
               password.charAt(1)  == '3' &&
               password.charAt(7)  == 'b' &&
               password.charAt(10) == '_' &&
               password.charAt(5)  == '4' &&
               password.charAt(9)  == '3' &&
               password.charAt(11) == 't' &&
               password.charAt(15) == 'c' &&
               password.charAt(8)  == 'l' &&
               password.charAt(12) == 'H' &&
               password.charAt(20) == 'c' &&
               password.charAt(14) == '_' &&
               password.charAt(6)  == 'm' &&
               password.charAt(24) == '5' &&
               password.charAt(18) == 'r' &&
               password.charAt(13) == '3' &&
               password.charAt(19) == '4' &&
               password.charAt(21) == 'T' &&
               password.charAt(16) == 'H' &&
               password.charAt(27) == '5' &&
               password.charAt(30) == '2' &&
               password.charAt(25) == '_' &&
               password.charAt(22) == '3' &&
               password.charAt(28) == '0' &&
               password.charAt(26) == '7' &&
               password.charAt(31) == 'e';
    }
    }
Dan Pada file tersbut kita tidak dapat mendapatkan sebuah password sama sekali . <br>
Akan tetapi kita disini mendapatkan sebuah susunan character acak pada bagian "password.charAt" dari situ kita dapat <br>
menyimpulkan bahwa susunan acak itu adalah flag . nah sekarang kita akan mencari tahu cara mengurutkan susunan tersebut.<br>
**Penyelesaian:** <br>
Karena kita tidak dapat mendapatkan flag dengan menjalakan file Java tersebut maka disini kita akan membuat sebuah <br>
Python Code untuk mengurutkan susunan tersbut.<br>

    passgw = [None] * 32
    
    passgw[0] = 'd' 
    passgw[29] = '9' 
    passgw[4] = 'r' 
    passgw[2] = '5' 
    passgw[23] = 'r' 
    passgw[3] = 'c' 
    passgw[17] = '4' 
    passgw[1] = '3' 
    passgw[7] = 'b' 
    passgw[10] = '_' 
    passgw[5] = '4' 
    passgw[9] = '3' 
    passgw[11] = 't' 
    passgw[15] = 'c' 
    passgw[8] = 'l' 
    passgw[12] = 'H' 
    passgw[20] = 'c' 
    passgw[14] = '_' 
    passgw[6] = 'm' 
    passgw[24] = '5' 
    passgw[18] = 'r' 
    passgw[13] = '3' 
    passgw[19] = '4' 
    passgw[21] = 'T' 
    passgw[16] = 'H' 
    passgw[27] = '5' 
    passgw[30] = '2' 
    passgw[25] = '_' 
    passgw[22] = '3' 
    passgw[28] = '0' 
    passgw[26] = '7' 
    passgw[31] = 'e'
    
    # < ''.join > Digunakan untuk menghilangkan tanda petik setelah di print 
    print(''.join(passgw))
  Dan jika kita jalankan python tersebut maka kita akan mendapatkan hasil seperti berikut: <br>
     
     d35cr4mbl3_tH3_cH4r4cT3r5_75092e
Nah disini kita sudah mendapatkan flagnya dan tinggal ditambahkan format flagnya .<br>
Flag : picoCTF{d35cr4mbl3_tH3_cH4r4cT3r5_75092e}
