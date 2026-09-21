# Dokumentasi Bahasa Formal

**Nama:** 
- I Gede Satria Adi Pratama
- MUHAMAD MATIN ANUGRAH PUJAYANTO 
**Mata Kuliah:** Teori Bahasa dan Automata  
**Minggu:** Week 1
---

## Definisi Bahasa

L = { w ∈ {a,b}* | w diawali 'a' dan diakhiri 'b' }

Artinya: semua string yang karakter pertamanya 'a' dan karakter terakhirnya 'b'.

---

## Alphabet

Σ = {a, b}

Hanya boleh memakai simbol 'a' dan 'b'.

---

## Rules

1. Karakter pertama harus 'a'.
2. Karakter terakhir harus 'b'.
3. Karakter tengah bebas, boleh 'a' atau 'b'.
4. Panjang minimal 2 karakter.

Regex: `a(a|b)*b`

---

## Valid Strings

| String | Alasan |
| :--- | :--- |
| `ab` | Awal 'a', akhir 'b' |
| `aab` | Awal 'a', akhir 'b' |
| `abb` | Awal 'a', akhir 'b' |
| `abab` | Awal 'a', akhir 'b' |
| `aaaaabbbbb` | Awal 'a', akhir 'b' |

---

## Invalid Strings

| String | Alasan |
| :--- | :--- |
| `ba` | Awal 'b', bukan 'a' |
| `a` | Tidak diakhiri 'b' |
| `b` | Tidak diawali 'a' |
| `aba` | Akhir 'a', bukan 'b' |
| `ε` | Kosong, panjang kurang dari 2 |

---

## DFA

```mermaid
stateDiagram-v2
    direction LR
    [*] --> q0
    q0 --> q1 : a
    q0 --> q3 : b

    q1 --> q1 : a
    q1 --> q2 : b

    q2 --> q1 : a
    q2 --> q2 : b

    q3 --> q3 : a, b
    q2 --> [*]
