# 🛡️ Implementasi Kriptografi Klasik: ROT13

[![Python Version](https://img.shields.io/badge/python-3.x-blue.svg)](https://www.python.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Course](https://img.shields.io/badge/Mata%20Kuliah-Hukum%20Cyber-red.svg)](#)

## 📝 Deskripsi Proyek
Repositori ini berisi implementasi algoritma enkripsi **ROT13** menggunakan Python. Proyek ini disusun untuk memenuhi tugas mata kuliah **Hukum Cyber**, guna mendemonstrasikan prinsip dasar kerahasiaan data (*Data Confidentiality*) melalui teknik kriptografi sederhana.

Dalam dunia hukum siber, pemahaman tentang enkripsi merupakan fondasi dalam mempelajari perlindungan data pribadi dan keamanan informasi.

---

## ⚙️ Cara Kerja Algoritma
ROT13 (*Rotate by 13 places*) adalah varian dari *Caesar Cipher*. Algoritma ini mengganti setiap huruf dengan huruf ke-13 setelahnya dalam urutan alfabet.

### Karakteristik Teknis:
| Fitur | Deskripsi |
| :--- | :--- |
| **Jenis** | Substitution Cipher |
| **Kunci** | Statis (13) |
| **Sifat** | Resiprokal (Enkripsi & Dekripsi menggunakan fungsi yang sama) |
| **Kompleksitas** | Rendah (Hanya untuk pengaburan teks, bukan keamanan tingkat tinggi) |

---

## 💻 Implementasi Kode
Kode ini dirancang untuk menangani huruf besar (*uppercase*) dan huruf kecil (*lowercase*) tanpa merubah simbol atau angka.

```python
def rot13_transform(text):
    transformed_text = ""
    for char in text:
        if 'a' <= char <= 'z':
            # Pergeseran modulo 26 untuk huruf kecil
            transformed_text += chr(((ord(char) - ord('a') + 13) % 26) + ord('a'))
        elif 'A' <= char <= 'Z':
            # Pergeseran modulo 26 untuk huruf besar
            transformed_text += chr(((ord(char) - ord('A') + 13) % 26) + ord('A'))
        else:
            transformed_text += char
    return transformed_text
