# 🛡️ Implementasi Kriptografi Klasik: ROT13

[![Python Version](https://img.shields.io/badge/python-3.x-blue.svg)](https://www.python.org/)
[![Course](https://img.shields.io/badge/Mata%20Kuliah-Hukum%20Cyber-red.svg)](#)

## 📝 Deskripsi Proyek
Repositori ini berisi implementasi algoritma enkripsi **ROT13** menggunakan Python. Proyek ini disusun untuk tugas mata kuliah **Hukum Cyber**, guna mendemonstrasikan prinsip dasar kerahasiaan data (*Data Confidentiality*) melalui teknik kriptografi sederhana.

Dalam perspektif hukum siber, pemahaman tentang enkripsi sangat penting karena berkaitan dengan aspek keamanan data dan perlindungan informasi pribadi (UU PDP).

---

## ⚙️ Cara Kerja Algoritma
ROT13 (*Rotate by 13 places*) adalah algoritma pergeseran alfabet. Karena alfabet memiliki 26 karakter, pergeseran sebanyak 13 posisi membuat proses enkripsi dan dekripsi menjadi identik.

### Karakteristik Teknis:
| Fitur | Deskripsi |
| :--- | :--- |
| **Jenis** | Substitution Cipher |
| **Logika** | Pergeseran 13 karakter ke belakang (modulo 26) |
| **Sifat** | Resiprokal (Fungsi yang sama untuk Enkripsi & Dekripsi) |

---

## 💻 Implementasi Kode (Sesuai `rot13.ipynb`)
Kode ini menggunakan manipulasi nilai ASCII untuk menggeser karakter tanpa merusak simbol atau tanda baca.

```python
def rot13_transform(text):
    transformed_text = ""
    for char in text:
        if 'a' <= char <= 'z':
            # Implementasi pergeseran mundur 13 posisi
            transformed_text += chr(((ord(char) - ord('a') - 13 + 26) % 26) + ord('a'))
        elif 'A' <= char <= 'Z':
            # Implementasi untuk huruf besar
            transformed_text += chr(((ord(char) - ord('A') - 13 + 26) % 26) + ord('A'))
        else:
            transformed_text += char
    return transformed_text
