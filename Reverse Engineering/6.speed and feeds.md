# Speed And Feeds
Category : Reverse Engineering <br>
# Description
There is something on my shop network running at nc mercury.picoctf.net 28067, but I can't tell what it is. Can you? <br>
# Hints 
What language does a CNC machine use? <br>
**Identifikasi:** <br>
Kita diberikan sebuah peritah netcat nc mercury.picoctf.net 28067 Dan jika di dijalankan maka akan keluar sebuah G-Codes <br>
    
    17 G21 G40 G90 G64 P0.003 F50
    G0Z0.1
    G0Z0.1
    G0X0.8276Y3.8621
    G1Z0.1
    G1X0.8276Y-1.9310
    G0Z0.1
    G0X1.1034Y3.8621
    G1Z0.1
    G1X1.1034Y-1.9310
    G0Z0.1
    G0X1.1034Y3.0345
    G1Z0.1
    G1X1.6552Y3.5862
    G1X2.2069Y3.8621
    G1X2.7586Y3.8621
    G1X3.5862Y3.5862
    G1X4.1379Y3.0345
    G1X4.4138Y2.2069
    G1X4.4138Y1.6552
  Sebenernya G-Codes yang diberikan sangat banyak , nah kita bisa copy semua G-Codes tersebut ke Dalam Leafpad / Notepad <br>
  **Penyelesaian:**<br>
Kita akan berfokus pada hint yang diberikan yaitu Bahasa Pemrograman CNC Yang tidak lain adalah G-Codes, Nah karena kita <br>
Sudah tau bahasa yang digunakan CNC maka kita bisa buka https://ncviewer.com/ Untuk melihat hasil dari G-Codes Tadi<br>
Dan Hasil Dari ncviewer tadi adalah: <br>
![image](https://github.com/NeloRedgrave/WriteUp_CTF/assets/140806028/79c1739a-b0f2-4b3e-8d57-eed0fde9ca96)
