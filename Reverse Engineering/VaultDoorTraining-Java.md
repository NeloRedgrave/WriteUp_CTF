# VaultDoorTraining
VaultDoorTraining.java <br>
https://jupiter.challenges.picoctf.org/static/a4a1ca9c54d8fac9404f9cbc50d9751a/VaultDoorTraining.java <br>
Description <br>
Your mission is to enter Dr. Evil's laboratory and retrieve the blueprints for his Doomsday Project. The laboratory is <br> protected by a series of locked vault doors. Each door is controlled by a computer and requires a password to <br> open. Unfortunately, our undercover agents have not been able to obtain the secret passwords for the vault doors, but <br> one of our junior agents obtained the source code for each vault's computer! You will need to read the source code<br> for each level to figure out what the password is for that vault door. As a warmup, we have created a replica<br> vault in our training facility. The source code for the training vault is here: _VaultDoorTraining.java_
Identifikasi:
Kita diberikan suatu file Java dan untuk menyelidiki file java tersebut maka yang pertama kita lakukan adalah melakukan run terhadap file java tersebut , akan tetapi saya masih belum bisa menjalakan file tersebut dikarenakan masih bingung dengan os Kali Linux. <br>
Penyelesaian: <br>
Kita akan membuka isi dari file java tersebut , dan ternyata ada sebuah flag yang ternyata sudah lengkap hanya tinggal format <br>

    public boolean checkPassword(String password) {
        return password.equals("w4rm1ng_Up_w1tH_jAv4_be8d9806f18");
Dan Disini kita hanya tinggal menambahkan format <br>
picoCTF{w4rm1ng_Up_w1tH_jAv4_be8d9806f18}
