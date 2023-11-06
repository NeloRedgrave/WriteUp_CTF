# Transformation
I wonder what this really is... enc <br>
''.join([chr((ord(flag[i]) << 8) + ord(flag[i + 1])) for i in range(0, len(flag), 2)]) <br>
  Penyelesaian: <br>
Pada file < enc > terdapat sebuah kalimat berbahasa mandarin , disitu kita dapat mengubah kalimat tersebut menjadi
hex < utf 16 to hex > dan setelah menjadi hex kita akan convert lagi menjadi ASCII < hex to ASCII > <br>
enc = 灩捯䍔䙻ㄶ形楴獟楮獴㌴摟潦弸弰摤捤㤷慽 <br>
UTF-16 to Hex = 7069636f4354467b31365f626974735f696e73743334645f6f665f385f30646463643937617d <br>
Hex to ASCII = picoCTF{16_bits_inst34d_of_8_0ddcd97a} <br>






