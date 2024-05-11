
# PCD_UTS_202231096_2024_ITPLN

Project ini adalah hasil pengerjaan UTS Pengolahan Citra Digital_D, dimulai dari : 

- Pengambilan citra
- Deteksi warna citra
- Menghitung nilai ambang batas warna citra

Project ini ditujukan kepada pengajar Pengolahan Citra Digital_D, agar dapat dinilai selesai.
## Authors

- Farrel Laogi Murjitama (202231096)


## Documentation

Pada tahap awal, yaitu dengan menentukan objek citra. Sesuai instruksi persoalan saya akan mengambil citra sebuah kertas yang tertulis nama lengkap peserta dengan 3 warna (Red, Green, Blue), dengan aturan lain yang diinstruksikan pengajar mata kuliah.

- Bahan citra saya = gambar2.jpg

Setelah bahan citra dipersiapkan, dilanjut dengan mengolah citra, peserta diinstruksikan menggunakan pemrograman phyton untuk memanipulasi keseluruhan citra. 
- Uraian algoritma pemrograman antara lain sebagai berikut: 

1. Mengambil citra, dan membuat file phyton baru.
2. Mendatangkan pustaka (import library), dan membaca file gambar.
File gambar sebelumnya berlokasi yang sama dengan file phyton.

3. Selanjutnya memproses citra untuk memanipulasi tingkat kontras, dengan menampilkan level kontras dalam bentuk histogram, dilanjut menaikkan kontras gambar yang dapat diatur melalui variabel 'beta'.
Variabel beta ini mengacu pada parameter yang digunakan dalam transformasi gamma. Transformasi gamma adalah fungsi non-linier yang digunakan untuk mengubah nilai piksel dalam citra. Transformasi ini didefinisikan sebagai:
O=I^β
β=var beta
di mana I adalah nilai piksel masukan, O adalah nilai piksel keluaran, dan β adalah variabel gamma. Nilai β dapat disesuaikan untuk mengendalikan kecerahan dan kontras dalam citra.

Ketika variabel beta ditingkatkan, transformasi gamma meningkat, yang mengarah pada perubahan tingkat kontras dalam citra. Peningkatan beta biasanya menghasilkan citra yang lebih cerah dengan kontras yang lebih tinggi. Namun, terlalu tinggi dapat menyebabkan hilangnya detail di daerah dengan intensitas cahaya rendah atau gelap.

4. Dilanjut program mendeteksi warna tunggal RGB (merah, hijau, biru) pada citra, dengan mengatur nilai Tentukan rentang warna citra yang telah dimanipulasi sebelumnya dalam skala HSV
'hsv = cv2.cvtColor(image, cv2.COLOR_RGB2HSV)
lower_warna=np.array([])
upper_warna=np.array([]);'

lalu menggunakan teknik masking untuk menyaring warna lain selain target warna

'var[(mask_not_targetwarna != 0)]= [0-255, 0-255, 0-255];'

Teknik masking dalam manipulasi citra adalah proses yang digunakan untuk membatasi area tertentu dalam citra yang akan diproses atau diperlakukan, sementara area lainnya diabaikan atau dibiarkan tidak berubah. Ini dilakukan dengan menerapkan maska atau "pembenam" pada citra, yang memungkinkan kita untuk menentukan area di mana operasi atau efek yang diterapkan, dan di mana tidak.

Operasi masking melibatkan kombinasi citra asli dengan maska untuk menghasilkan citra yang diinginkan. Misalnya, kita dapat menggunakan operasi bitwise AND untuk menerapkan maska pada citra. Dalam operasi ini, setiap piksel dalam citra hasil akan menjadi nilai piksel asli jika nilai piksel maska di lokasi yang sesuai adalah 1, dan menjadi hitam (0) jika maska adalah hitam (0)

selanjutnya menyajikan gambar dalam bentuk histogram seperti sebelumnya.

5. Terakhir memanipulasi ambang batas citra dengan menyisipkan fungsi untuk menghitung ambang batas dengan keseluruhan program deteksi warna sebelumnya, hanya menambahkan:
"# Fungsi untuk mencari nilai ambang batas warna hijau
def find_warna_threshold(image):
    hsv = cv2.cvtColor(image, cv2.COLOR_BGR2HSV)
    hist = cv2.calcHist([hsv], [0], None, [180], [0, 180])
    warna_threshold = np.argmax(hist)
    return warna_threshold"

'#Mencari nilai ambang batas warna

warna_threshold = find_warna_threshold(image)'
berdasarkan hasil percobaan ambang batas semua warna bernilai 75, ini mungkin karena filter yang digunakan menyaring warna menjadi warna grayscale.

Ambang batas warna (color thresholding) adalah teknik yang digunakan dalam pengolahan citra untuk mengidentifikasi piksel-piksel dalam suatu citra yang memiliki nilai warna tertentu atau berada dalam rentang warna tertentu. Teknik ini berguna dalam segmentasi citra, di mana tujuannya adalah untuk memisahkan objek atau area tertentu dalam citra berdasarkan warnanya.

Ambang batas dapat ditentukan secara manual berdasarkan pemahaman tentang warna yang ingin diidentifikasi, atau dapat ditentukan secara otomatis dengan menggunakan metode pemrosesan citra, seperti Otsu's method atau Adaptive Thresholding, untuk menentukan nilai ambang batas secara adaptif berdasarkan histogram citra.
## 🔗 Links
[![portfolio](https://img.shields.io/badge/my_github-000?style=for-the-badge&logo=ko-fi&logoColor=white)](https://github.com/FarrelLOM/PCD_UTS_202231096_2024_ITPLN.git)
