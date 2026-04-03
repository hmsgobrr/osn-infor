# Logika Dasar dan Operasi Bitwise

## Logika Dasar

### Proposisi

Proposisi adalah kalimat yang dapat ditentukan dengan jelas benar atau salahnya. Misalnya, "4 adalah angka genap" dan "$5\in\{1,2,3,4,5\}$" adalah proposisi.

### Operasi Logika

Ada beberapa cara untuk menggabungkan beberapa proposisi untuk membuat proposisi baru yang lebih kompleks. Dalam bahasa, kita dapat menggunakan konjungsi seperti "dan", "atau", "jika ..., maka ...", dan lain-lain. Secara formal terdapat sejumlah **operasi logika**:

- Konjungsi, *dan* ($p \wedge q$): hanya benar kalau $p$ dan $q$ keduanya benar.
- Disjungsi, *atau* ($p \vee q$): benar kalau salah satu atau kedua dari $p$ dan $q$ benar.
- Negasi, *tidak* ($\neg{p}$): benar kalau $p$ salah.
- Implikasi, *"Jika $p$, maka $q$."* ($p \rightarrow q$): Kalau $q$ benar tapi $p$ salah masih mungkin, karena penyebab $q$ belum tentu hanya $p$. Namun, kalau $p$ benar sementara $q$ salah, ini bertentangan sehingga $p \rightarrow q$ akan salah.
- Biimplikasi, *"Jika p, maka q dan sebaliknya."* ($p \leftrightarrow q$), ini ekuivalen dengan $(p \rightarrow q) \wedge (p \leftarrow q)$

Berikut adalah **tabel kebenaran** yang menunjukkan kebenaran proposisi berdasarkan kondisi $p$ dan $q$ dengan 0 adalah salah dan 1 adalah benar:

| p | q | $p \wedge q$ | $p \vee q$ |
|:-:|:-:|:-:|:-:|
| 0 | 0 | 0 | 0 |
| 0 | 1 | 0 | 1 |
| 1 | 0 | 0 | 1 |
| 1 | 1 | 1 | 1 |

| p | q | $p \rightarrow q$ | $p \leftarrow q$ | $p \leftrightarrow q$ |
|:-:|:-:|:-:|:-:|:-:|
| 0 | 0 | 1 | 1 | 1 |
| 0 | 1 | 1 | 0 | 0 |
| 1 | 0 | 0 | 1 | 0 |
| 1 | 1 | 1 | 1 | 1 |

| p | $\neg p$ |
|:-:|:-:|
| 0 | 1 |
| 1 | 0 |

### Tatutologi dan Kontradiksi

Ada beberapa proposisi yang, dalam semua kondisi, selalu bernilai benar. Proposisi tersebut disebut **tautologi**. Berikut adalah beberapa contohnya:

- $\neg(p \wedge q) \leftrightarrow (\neg{p} \vee \neg{q})$
- $p \vee \neg{p}$
- $(p \wedge q) \rightarrow p$
- $q \rightarrow (p \vee q)$
- $(p \vee q) \leftrightarrow (q \vee p)$

Sebaliknya, jika suatu proposisi bernilai salah dalam semua kasus, maka proposisi tersebut adalah **kontradiksi**. Contohnya adalah:

- $p \wedge \neg{p}$
- $(p \vee q) \wedge \neg{p} \wedge \neg{q}$

### Ekuivalensi

Perhatikan dua proposisi: $\neg(p \wedge q)$ dan $(\neg{p} \vee \neg{q})$. Sekilas, kedua proposisi terlihat berbeda. Secara bentuk memang berbeda. Namun, sebetulnya kedua proposisi sama saja (ekuivalen). Hal ini mungkin lebih terbayang jika dimisalkan dengan kalimat:

- $p$ adalah "saya suka pisang"
- $q$ adalah "saya suka apel"

sehingga...

- $\neg(p \wedge q)$ adalah "saya tidak suka pisang dan apel" (menyukai salah satu masih mungkin)
- $\neg{p} \vee \neg{q}$ adalah "saya tidak suka pisang atau saya tidak suka apel"

Bila diuji dengan kasus yang sama, hasil kedua proposisi pasti akan sama. Agar lebih jelas, ekuivalensi dua proposisi dapat dilihat dari tabel kebenarannya:

| p | q | $\neg(p \wedge q)$ | $\neg{p} \vee \neg{q}$ |
|:-:|:-:|:-:|:-:|
| 0 | 0 | 1 | 1 |
| 0 | 1 | 1 | 1 |
| 1 | 0 | 1 | 1 |
| 1 | 1 | 0 | 0 |

Dua proposisi ekuivalen jika tabel kebenarannya identik. Hal ini juga bisa dilihat dari apakah dihasilkan tautologi ketika digunakan biimplikasi pada keduanya. Karena $\neg(p \wedge q) \leftrightarrow (\neg{p} \vee \neg{q})$ adalah tautologi, $\neg(p \wedge q)$ ekuivalen dengan $(\neg{p} \vee \neg{q})$

### Hukum-Hukum Logika

Dibawah ini terdapat beberapa hukum yang dapat digunakan untuk memanipulasi bentuk proposisi. $r \Leftrightarrow s$ menyatakan bahwa proposisi $r$ dan $s$ ekuivalen.

| Hukum         | Bentuk                                    |
| ------------- | ----------------------------------------- |
| Komutatif     | $p \vee q \Leftrightarrow q \vee p$       |
|               | $p \wedge q \Leftrightarrow q \wedge p$   |
| Asiosiatif    | $(p \vee q) \vee r \Leftrightarrow p \vee (q \vee r)$ |
|               | $(p \wedge q) \wedge r \Leftrightarrow p \wedge (q \wedge r)$ |
| Distributif   | $p \wedge (q \vee r) \Leftrightarrow (p \wedge q) \vee (p \wedge r)$ |
|               | $p \vee (q \wedge r) \Leftrightarrow (p \vee q) \wedge (p \vee r)$ |
| Identitas     | $p \vee 0 \Leftrightarrow p$ |
|               | $p \wedge 1 \Leftrightarrow p$ |
| H. Negasi     | $p \wedge \neg{p} \Leftrightarrow 0$ |
|               | $p \vee \neg{p} \Leftrightarrow 1$ |
| H. Idempoten  | $p \vee p \Leftrightarrow p$|
|               | $p \wedge p \Leftrightarrow p$|
| H. *Null*     | $p \wedge 0 \Leftrightarrow 0$ |
|               | $p \vee 1 \Leftrightarrow 1$ |
| H. Penyerapan | $p \wedge (p \vee q) \Leftrightarrow p$ |
|               | $p \vee (p \wedge q) \Leftrightarrow p$ |
| H. DeMorgan   | $\neg(p \vee q) \Leftrightarrow \neg{p} \wedge \neg{q}$ |
|               | $\neg(p \wedge q) \Leftrightarrow \neg{p} \vee \neg{q}$ |
| H. Involusi   | $\neg(\neg{p}) \Leftrightarrow p$ |

### Operasi Tambahan: XOR

Dalam elektronika dan ilmu komputer, terdapat operasi tambahan selain *dan* serta *atau* yang dinamakan **Exclusive or (XOR)**. Simbol yang digunakan untuk XOR, antara lain, adalah $\oplus$. Hasil operasi ini, yakni $p \oplus q$ bernilai benar jika dan hanya jika **salah satu** antara $p$ dan $q$ benar dan satunya lagi salah:

| p | q | $p \oplus q$ |
| - | - | - |
| 0 | 0 | 0 |
| 0 | 1 | 1 |
| 1 | 0 | 1 |
| 1 | 1 | 0 |

Operasi XOR ekuivalen dengan $(p \wedge \neg{q}) \vee (\neg{p} \wedge q)$ dan negasi dari biimplikasi $\neg(p \leftrightarrow q)$.

## Operasi Bitwise

Operasi logika (*dan*, *atau*, dll.) bisa dibilang merupakan bagian yang tidak terpisahkan dalam komputer. Tidak hanya dalam mengolah variabel boolean, tetapi operasi logika juga menjadi dasar sebagian besar komputasi karena data tersimpan dalam bentuk biner. CPU komputer sendiri terdiri dari [gerbang logika](https://en.wikipedia.org/wiki/Logic_gate) yang pada dasarnya adalah operasi logika.

Dalam C/C++, selain operasi aritmatika umum seperti tambah, kali, kurang, dan bagi, ada operasi **bitwise** yang memperbolehkan manipulasi angka sebagai bilangan biner. Operasi bitwise yang tersedia adalah sebagai berikut:

| Operasi           | Penggunaan |
| ----------------- | - |
| AND (&)           | `a & b` |
| OR (\|)            | `a | b` |
| XOR (^)           | `a ^ b` |
| NOT (~)           | `~a` |
| Left shift (<<)   | `a << b` |
| Right shift (>>)  | `a >> b` |

Yang membedakan bitwise dengan operator boolean biasa seperti AND (&&) dan OR (||) adalah bahwa operator bitwise menerima bilangan biasa (1, 2, 3, dst.) bukan hanya boolean (0 atau 1).

Hasil dari suatu operasi bitwise (selain left shift dan right shift) adalah bilangan yang didapatkan dari operasi logikanya pada setiap digit (dalam bentuk biner) kedua bilangan.

Misalnya, operasi AND dari `12 & 6` akan menghasilkan 8. Ini dapat dihitung dengan mengubah 12 dan 6 menjadi bentuk binernya kemudian meng-AND-kan setiap digitnya:

$$
\begin{array}{r}
      1100_2 \\
_\&\; 0110_2 \\ \hline
      1000_2
\end{array}
$$

Dengan cara yang sama, hasil `12 | 6` dan `12 ^ 6` dapat dihitung menghasilkan 14 dan.

$$
\begin{array}{r}
     1100_2 \\
_|\; 0110_2 \\ \hline
     1110_2
\end{array}
\qquad
\begin{array}{r}
     1100_2 \\
_\wedge\; 0110_2 \\ \hline
     1110_2
\end{array}
$$

Di sisi lain, operator NOT (~) akan membalikkan setiap bit dalam bilangan dari 0 menjadi 1 dan sebaliknya tergantung berapa banyak digit yang dipakai. Untuk biner 4 digit ~12 akan menghasilkan 3.

$$
\sim{1100_2} = 0011_2
$$

Terdapat juga operator bitwise yang tidak berkaitan dengan operator logika yakni operator left shift (<<) dan right shift (>>). `a << b` "menggeser" digit biner ke kiri b kali, menambahkan b buah 0 di kanan:

$$
1010_2 << 3 = 101000_2
$$

Sebaliknya `a >> b` "menggeser" ke a kanan b kali, menghilangkan b digit terkanan:

$$
1010_2 >> 3 = 1_2
$$

Bila diperhatikan, karena kedua operator digunakan untuk biner, `a << b` sama saja mengalikan a dengan $2^b$ dan `a >> b` sama saja membagi a dengan $2^b$ kemudian membulatkannya ke bawah.

## Sumber
- [Applied Discrete Structures (Doerr and Levasseur)](https://math.libretexts.org/Bookshelves/Combinatorics_and_Discrete_Mathematics/Applied_Discrete_Structures_(Doerr_and_Levasseur))
- [Bitwise Operators in C](https://www.geeksforgeeks.org/c/bitwise-operators-in-c-cpp/)
