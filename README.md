## Introduction to Flutter and Dart Programming Language
### Flutter
Flutter adalah sebuah toolkit open-source yang memungkinkan pembuatan aplikasi mobile dengan satu codebase untuk berbagai platform (Android, iOS, dan Web). Dikembangkan oleh Google, Flutter mengkompilasi kode Dart menjadi kode native, memberikan performa hampir setara dengan aplikasi native.
### Keunggulan Flutter
- Cross-platform: Dapat membuat aplikasi untuk Android dan iOS menggunakan satu kode sumber.
- Kecepatan: Pengembangan aplikasi yang cepat berkat hot reload dan banyak tools siap pakai.
- Performa: Kinerja aplikasi hampir setara dengan aplikasi native.
- Komunitas: Flutter memiliki komunitas yang besar, termasuk di Indonesia.
## Dart Programming Language
Dart adalah bahasa pemrograman yang dikembangkan oleh Google, digunakan untuk membangun aplikasi frontend di platform mobile, web, dan desktop. Dart mengadopsi paradigma Object-Oriented Programming (OOP) dan mendukung tipe data kuat (strongly-typed).
## 1. Variabel dan Tipe Data
- Deklarasi Variabel
```
var nama = "Rahmah Aisyah"; 
int umur = 18;
```
- Null Safety: Untuk mengizinkan variabel menyimpan nilai null, gunakan tanda ?
```
int? number2; 
```
- Final dan Const
```
final String nama = "Rahmah"; // Tidak bisa diubah setelah inisialisasi
const double pi = 3.14;       // Nilai konstan, diketahui saat kompilasi
```
## 2. Fungsi
- Deklarasi Fungsi
```
void sapa(String nama) {
  print("Halo, $nama!");
}
sapa("Rahmah");
```
- Arrow Function: Sintaks ringkas untuk fungsi
```
int tambah(int a, int b) => a + b;
```
## 3. Struktur Data
- List
```
final mahasiswa = ["Rahmah", "Aisyah", "Hanifah"];
print(mahasiswa[1]); // Output: Aisyah
```
- Map
```
final contohMap = {"nama": "Rahmah", "umur": 20};
print(contohMap["nama"]); // Output: Rahmah
```
## 4. Object-Oriented Programming (OOP)
- Class dan Object
```
class Mahasiswa {
  String nama;
  int umur;
  //constructor
  Mahasiswa(this.nama, this.umur);
  //metode
  void berjalan() {
    print("$nama sedang berjalan.");
  }
}

void main() {
  //object
  final mahasiswa = Mahasiswa("Rahmah Aisyah", 18);
  print(mahasiswa.nama);  // Output: Rahmah Aisyah
  mahasiswa.berjalan();   // Output: Rahmah Aisyah sedang berjalan.
}
```
- Inheritance: mewarisi atribut dan metod pada super class/induk class
```
class Hewan {
  void bergerak() {
    print("Hewan bergerak");
  }
}

class Kucing extends Hewan {
  void mengeong() {
    print("Kucing mengeong");
  }
}

void main() {
  final kucing = Kucing();
  kucing.bergerak(); // Output: Hewan bergerak
  kucing.mengeong(); // Output: Kucing mengeong
}
```
- Extension: Menambahkan method baru ke tipe data
```
extension StringExtension on String {
  String reverse() {
    return split('').reversed.join();
  }
}

void main() {
  print("Dart".reverse()); // Output: traD
}
```
## 5. Error Handling
Dart mendukung `try`, `catch`, dan `finally` untuk menangani error
```
void main() {
  try {
    int? nilai = null;
    if (nilai == null) {
      throw Exception("Nilai tidak boleh null!");
    }
  } catch (e) {
    print("Terjadi kesalahan: $e");
  } finally {
    print("Proses selesai.");
  }
}
```
## 6. Enum dan Dynamic
- Enum
```
enum Status { aktif, tidakAktif, pending }

void main() {
  Status statusPengguna = Status.aktif;
  print(statusPengguna); // Output: Status.aktif
}
```
- Dynamic
```
dynamic data = "Halo";
data = 123; // Tidak disarankan karena mengurangi kejelasan tipe data
```
## 7. Mixins
Mixins adalah fitur Dart yang memungkinkan kita untuk berbagi kode antar kelas tanpa menggunakan pewarisan (inheritance) secara langsung. Mixins cocok digunakan ketika suatu kelas perlu menambahkan fungsi tertentu tetapi tidak relevan dengan hirarki pewarisan.
```
// Mixins tidak memiliki constructor.
mixin BisaTerbang {
  void terbang() {
    print("Saya bisa terbang!");
  }
}

// Kelas Utama
class Hewan {
  void berjalan() {
    print("Saya bisa berjalan.");
  }
}

// Gunakan keyword with untuk menambahkan mixins ke dalam kelas.
class Burung extends Hewan with BisaTerbang {}

void main() {
  final burung = Burung();
  burung.berjalan();  // Output: Saya bisa berjalan.
  burung.terbang();   // Output: Saya bisa terbang!
}
```
