# Jankenpon-CV2
Klasifikasi gambar Gunting, Batu, Kertas dengan pendekatan classic machine learning dengan melakukan ekstraksi fitur HOG

## Dataset
Dataset didapat dari Drgfreeman di Kaggle https://www.kaggle.com/datasets/drgfreeman/rockpaperscissors dengan banyak data sebagai berikut:

| Jenis Gambar | Banyaknya |
| -- | -- |
| Batu | 726 |
| Gunting | 750 |
| Kertas | 712 |

Semua ukuran gambar sama yaitu 300x200 dengan format .png data juga dipisah menjadi data train dan data test dengan perbandingan 80:20.

## Ekstraksi Fitur
Menggunakan hog dari skimage.feature sehingga didapatkan ukuran dataframe (726+760+712)x65205=2188x65205 (tidak termasuk label/target). Untuk mempercepat runtime, juga dilakukan seleksi fitur dengan Random Forest Feature Importance dengan membuang nilai importance = 0 sehingga didapatkan dimensi dataframe akhir  2188x12023 (tidak termasuk label/target)

## Model
Dengan menggunakan Multi Layer Perceptron dari Scikit Learn menggunakan parameter default.

## Hasil dan Perbandingan dengan Sebelumnya
| Repository | Akurasi Data Train | Akurasi Data Test |
| -- | -- | -- |
| [Jankenpon-CV](https://github.com/Otniel113/Jankenpon-CV) | 0.642 | 0.342 |
| [Jankenpon-CV2](https://github.com/Otniel113/Jankenpon-CV2) | 0.948 | 0.965 |
