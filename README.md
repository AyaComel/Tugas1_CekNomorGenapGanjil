# Tugas1_CekNomorGenapGanjil
 Tugas1-Cahya Hayyuni-2210010118
 
## 1. Deskripsi Program:
• GUI terdiri dari JTextField untuk input angka dan tombol Cek

• Saat tombol ditekan, program akan memvalidasi input dan
menampilkan hasilnya pada JLabel

## 2. Komponen GUI: 
JFrame, JPanel, JLabel, JTextField, JButton
- JTextField: Untuk input angka.
- JButton: Tombol untuk memeriksa angka.
- JLabel: Untuk menampilkan hasil pemeriksaan (Genap/Ganjil). 

## 3. Logika Program: 
Kondisional (if-else), Validasi input
- Implementasikan logika di tombol cekButton untuk memeriksa apakah angka yang dimasukkan adalah genap atau ganjil.
- Gunakan kondisional if-else untuk memisahkan angka genap dari ganjil.
- Tambahkan validasi untuk memastikan input hanya angka.

## 4. Events:
A.ActionListener untuk tombol Cek
~~~
private void cekButtonActionPerformed(java.awt.event.ActionEvent evt) {                                          
   try {
         int angka = Integer.parseInt(inputField.getText());
         String hasil = "Angka " + angka;

         // Mengecek apakah angka genap atau ganjil
         if (angka % 2 == 0) {
             hasil += " adalah Genap";
         } else {
             hasil += " adalah Ganjil";
         }

         // Mengecek apakah angka prima
         if (isPrime(angka)) {
             hasil += " dan bilangan prima";
         } else {
             hasil += " dan bukan bilangan prima";
         }

         // Menampilkan hasil
         JOptionPane.showMessageDialog(this, hasil, "Hasil", JOptionPane.INFORMATION_MESSAGE);
     } catch (NumberFormatException e) {
         JOptionPane.showMessageDialog(this, "Masukkan angka yang valid!", "Error", JOptionPane.ERROR_MESSAGE);
     }
~~~
B.KeyAdapter pada JTextField untuk membatasi input hanya angka
~~~
if (!Character.isDigit(evt.getKeyChar())) {
         evt.consume();
     }
~~~
5. Variasi:
• Tambahkan fitur untuk memeriksa apakah angka tersebut adalah bilangan prima
~~~
// Mengecek apakah angka prima
    if (isPrime(angka)) {
             hasil += " dan bilangan prima";
    } else {
             hasil += " dan bukan bilangan prima";
    }

private boolean isPrime(int number) {
        if (number <= 1) return false;
        for (int i = 2; i <= Math.sqrt(number); i++) {
            if (number % i == 0) return false;
        }
        return true;
     }
 ~~~
• Gunakan JOptionPane untuk menampilkan pesan hasil dan error
 ~~~
 } catch (NumberFormatException e) {
         JOptionPane.showMessageDialog(this, "Masukkan angka yang valid!", "Error", JOptionPane.ERROR_MESSAGE);
     }

~~~
• Implementasikan FocusListener untuk membersihkan JTextField saat mendapatkan focus
~~~
private void inputFieldFocusGained(java.awt.event.FocusEvent evt) {                                       
   inputField.setText("");
    } 
~~~

## Contoh Gambar Project Setelah di Run
![](https://github.com/firaaaa10/Tugas1_AplikasiCekNomorGenapAtauGanjil/blob/main/Cuplikan%20layar%202024-11-04%20102016.png)
 

## Indikator Penilaian:

| No  | Komponen         |  Persentase  |
| :-: | --------------   |   :-----:    |
|  1  | Komponen GUI     |    20    |
|  2  | Logika Program   |    20    |
|  3  | Events           |    15    |
|  4  | Kesesuaian UI    |    15    |
|  5  | Memenuhi Variasi |    30    |
|     | TOTAL        | 100 |

## Pembuat

Nama   : Cahya Hayyuni
NPM    : 2210010118
