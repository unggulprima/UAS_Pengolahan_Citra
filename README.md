# UAS_Pengolahan_Citra

# UAS---PENGOLAHAN-CITRA---TI.22.A.5
| NAMA | NIM |
| - | - |
| Unggul Prima Dhani | 312210477 |
| Fazlurrahman busa duru  | 312210522 |
| Muhammad Arley Alfaridzi  | 312210631 |
| Muhammad Abdullah Azzam| 312210484 |


import Library

import numpy as np
import matplotlib.pyplot as plt
import cv2


Baca tiga gambar dari file

image1 = cv2.imread('images/semangka 1.jpg')
image2 = cv2.imread('images/semangka 2.jpg')
image3 = cv2.imread('images/semangka 3.jpg')


Periksa apakah semua gambar berhasil dibaca

if image1 is None or image2 is None or image3 is None:
    print("Salah satu atau lebih gambar tidak ditemukan")
else:


Ubah warna dari BGR ke RGB untuk ketiga gambar

    image1_rgb = cv2.cvtColor(image1, cv2.COLOR_BGR2RGB)
    image2_rgb = cv2.cvtColor(image2, cv2.COLOR_BGR2RGB)
    image3_rgb = cv2.cvtColor(image3, cv2.COLOR_BGR2RGB)


Sesuaikan ukuran gambar jika diperlukan agar memiliki tinggi yang sama

    height = min(image1.shape[0], image2.shape[0], image3.shape[0])
    image1_rgb = cv2.resize(image1_rgb, (int(image1.shape[1] * height / image1.shape[0]), height))
    image2_rgb = cv2.resize(image2_rgb, (int(image2.shape[1] * height / image2.shape[0]), height))
    image3_rgb = cv2.resize(image3_rgb, (int(image3.shape[1] * height / image3.shape[0]), height))


Gabungkan ketiga gambar secara horizontal

combined_image = cv2.hconcat([image1_rgb, image2_rgb, image3_rgb])


Tampilkan gambar gabungan

    plt.imshow(combined_image)
    plt.axis('off')  # Menyembunyikan sumbu
    plt.show()


## hasil output
