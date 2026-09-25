---
title: Kalkulator Sederhana
sidebar_position: 1
---

# Kalkulator Sederhana

Kalkulator berbasis terminal ini menerima dua angka dan satu operator, lalu menampilkan hasil perhitungannya.

## Operasi yang didukung

| Operator | Operasi |
| --- | --- |
| `+` | Penjumlahan |
| `-` | Pengurangan |
| `*` | Perkalian |
| `/` | Pembagian |

## Cara menggunakan

1. Jalankan skrip menggunakan Python.
2. Masukkan angka pertama saat prompt `Angka 1:` muncul.
3. Masukkan salah satu operator yang didukung.
4. Masukkan angka kedua.
5. Hasil perhitungan ditampilkan dengan awalan `Hasil:`.

Contoh alur penggunaan:

```text
Angka 1: 11
Operator (+, -, *, /): *
Angka 2: 4
Hasil: 40.0
```

Input angka dikonversi menjadi bilangan desimal (`float`), sehingga aplikasi dapat menerima nilai seperti `5`, `2.5`, atau `-3.75`.

## Perilaku input

- Operator `+`, `-`, `*`, dan `/` menghasilkan perhitungan yang sesuai.
- Operator lain menghasilkan keluaran:

  ```text
  Hasil: Invalid
  ```

- Input angka yang tidak dapat dikonversi menjadi `float` menyebabkan program berhenti dengan kesalahan konversi.
- Angka kedua bernilai `0` menyebabkan kesalahan pembagian dengan nol. Karena seluruh operasi dihitung saat kumpulan hasil dibuat, keterbatasan ini juga berlaku ketika operator yang dipilih bukan `/`.

## Catatan implementasi

Hasil setiap operasi disimpan dalam pemetaan berdasarkan simbol operator. Operator dari pengguna digunakan untuk mengambil hasil yang sesuai, sedangkan operator yang tidak tersedia mengembalikan nilai `Invalid`.