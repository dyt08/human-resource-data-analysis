# Human Resource Data Analysis

by Aditya Nugraha

## Data Understanding
- Sumber Database: https://drive.google.com/file/d/1XfhOHYKzW7Cz1RNHlknJI6Lz7LLSi5EI/view?usp=sharing
- Tim HR atau Human Resource dari sebuah perusahaan e-commerce terkenal yang beroperasi di wilayah Amerika dan Eropa ingin mengetahui gambaran umum tentang kepegawaian di tempat perusahaannya bekerja. Terdapat sebuah database yang berisi detail karyawan berserta status kepegawaiannya. dari database tersebut, Tim HR ingin bisa mendapatkan gambaran bagaimana kondisi dari perusahaannya bekerja seperti banyaknya karyawan di setiap cabang, besaran dan kesesuaian gaji karyawan di setiap posisinya. 
- Diharapkan dari hasil analisis ini dapat membantu menjawab pertanyaan-pertanyaan seperti: apakah ada karyawan yang gajinya terlalu tinggi atau terlalu rendah dibanding karyawan lain di posisi yang sama, apakah pada cabang tertentu ada terlalu banyak karyawan, dan lain sebagainya. keputusan ini juga yang nantinya dapat digunakan untuk membantu tim HR untuk membuat keputusan strategis kedepannya terutama jika data hasil analisis ini digabungkan dengan data analisis lainnya. contoh keputusan bisnis yang diambil bisa berupa penundaan atau percepatan kenaikan gaji, pemindahan karyawan ke cabang lain, perekrutan karyawan, dan sebagainya.
- Database memiliki 7 tabel yang masing-masing memiliki informasi karyawan dan pekerjaannya
- Dari 7 tabel diambil dan dibagi menjadi 2 dataframe yaitu raw_data yang berisikan 110 baris, 25 kolom, dan job_grades yang berisikan 19 baris dan 11 kolom
- Tabel ERD:  

![HR ERD](Datasets/HR/HR%20ERD.gif)

- Database Dictionary:
  - employees: Berisi data karyawan yang ada
  - jobs: Berisi posisi pekerjaan beserta standar gaji minimal dan maximal yang telah ditetapkan pada masing-masing posisi
  - job_history: Berisi tanggal keluar-masuk karyawan beserta jabatannya
  - departments: Berisi detail departemen
  - locations: berisi detail lokasi dari departemen
  - countries: berisi detail negara dari lokasi departemen
  - regions: berisi detail wilayah dari lokasi departemen

- raw_data Dictionary:
  - employees: employee_id, first_name, last_name, email, phone_number, hire_date, salary, commission_pct, job_id, department_id, manager_id
  - jobs: job_title, min_salary, max_salary
  - job_history: start_date, end_date
  - departments: department_name, location_id
  - locations: street_address, postal_code, city, state_province, country_id
  - countries: country_name, region_id
  - regions: region_name
  
- job_grades Dictionary:
  - job_title: nama jabatan
  - min_salary: gaji minimal yang telah ditetapkan pekerjaan tersebut
  - max_salary: gaji maksimal yang telah ditetapkan pekerjaan tersebut
  - avg_salary: rata-rata gaji berdasarkan min_salary dan max_salary
  - grade_level: tinggakatan jabatan berdasarkan avg_salary
  - current_min_salary: gaji minimal pada karyawan saat ini
  - current_max_salary: gaji maksimal pada karyawan saat ini
  - current_avg_salary: rata-rata gaji berdasarkan current_min_salary dan current_max_salary
  - salary_count: banyaknya karyawan pada masing-masing jabatan
  - grade_level_by_current: tinggakatan jabatan berdasarkan current_avg_salary

## Data Manipulation
- Pada tabel raw_data dan job_grades masing-masing akan dilakukan pengecekan anomali datanya. Jika memang terdapat hal-hal yang dianggap 'kotor' pada data, maka yang perlu dilakukan adalah melakukan penanganan pada bagian tersebut. Pada bagian ini, data akan 'dibersihkan', sehingga ketika fitur tersebut dipanggil maka diharapkan data tersebut sudah bersih dan siap di analisis lebih lanjut.
- Merubah tipe data yang tidak sesuai
- Pengecekan missing value dan menanganinya
- Pengecekan duplikasi data

## Data Visualization & Statistics
- Pencarian data oulier dan distribusi datanya menggunakan fungsi histplot dan boxplot, serta menghitung jenis distribusinya, dan batas outliernya
- Memvisualisasikan Banyaknya Karyawan Berdasarkan Jabatan menggunakan fungsi barplot pada seaborn
- Memvisualisasikan Banyaknya Karyawan Berdasarkan Departemen menggunakan fungsi barplot pada seaborn
- Memvisualisasikan Banyaknya Karyawan Berdasarkan Lokasi Kota Departemennya menggunakan fungsi barplot pada seaborn
- Mengecek dan Memvisualisasikan Perbandingan Besaran Gaji Karyawan Berdasarkan Jabatan menggunakan fungsi barplot pada seaborn
- Melihat Linearitas & Hubungan pada Gaji Karyawan menggunakan fungsi regplot dan heatmap
- Menguji Normalitas Pada Data Gaji Karyawan menggunakan fungsi shapiro
- Melakukan Uji Perbandingan Median Besaran Gaji Karyawan pada Setiap Jabatan menggunakan fungsi kruskal
- Melakukan Uji Perbandingan Median Besaran Gaji di Setiap Cabang Berdasarkan Wilayah menggunakan fungsi mannwhitneyu
