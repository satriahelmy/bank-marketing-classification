# bank-marketing-classification

Pada notebook ini, berisi code mengenai Marketing Data Classification.

Input dari permasalahan ini adalah data bank client data campaign terakhir dan data social economy. Kemudian kita gunakan Random Forest untuk memprediksi apakah client akan berlangganan deposito atau tidak.

Dataset yang digunakan dapat diakses pada halaman berikut : http://archive.ics.uci.edu/ml/datasets/Bank+Marketing

Dataset yang digunakan adalah dataset bank marketing yang berisi data bank client, data campaign terakhir dan data sosial ekonomi. Terdapat 41188 baris dengan 20 kolom input dan 1 kolom output yang berisi informasi client subscribe atau tidak. Proporsi data outputnya adalah imbalanced (0.88 dibanding 0.11)

**Bank Marketing Data**:

- `age` : umur klien (numeric)
- `job` : pekerjaan (categorical: "admin.","blue-collar","entrepreneur","housemaid","management","retired","self-employed","services","student","technician","unemployed","unknown")
- `marital` : status perkawinan (categorical: "divorced","married","single","unknown"; note: "divorced" means divorced or widowed)
- `education` : pendidikan (categorical: "basic.4y","basic.6y","basic.9y","high.school","illiterate","professional.course","university.degree","unknown")
- `default`: memiliki kredit yang default? (binary: "yes", "no")
- `balance`: saldo tahunan rata-rata dalam euro (numeric)
- `housing`: memiliki pinjaman perumahan? (binary: "yes", "no")
- `loan`: memiliki pinjaman pribadi? (binary: "yes", "no")

<br>

**Kondisi komunikasi dengan campaign terakhir**
- `contact`: tipe kontak (categorical: "unknown", "telephone", "cellular")
- `day`: hari terakhir kontak (numeric)
- `month`: bulan terakhir kontak (categorical: "jan", "feb", "mar", ..., "nov", "dec")
- `duration`: durasi kontak terakhir dalam seconds (numeric)

<br>

**Atribut/Fitur lain**
- `campaign`: jumlah kontak dalam campaign(numeric, includes last contact)
- `pdays`: jumlah hari yang berlalu setelah klien terakhir dihubungi dari kampanye sebelumnya (numeric, -1 means client was not previously contacted)
- `previous`: jumlah kontak yang dilakukan sebelum kampanye ini(numeric)
- `poutcome`: hasil dari kampanye pemasaran sebelumnya (categorical: "unknown","other","failure","success")

<br>

**Kondisi sosial ekonomi**
- `emp.var.rate`: employment variation rate - quarterly indicator (numeric)
- `cons.price.idx`: consumer price index - monthly indicator (numeric)     
- `cons.conf.idx`: consumer confidence index - monthly indicator (numeric)     
- `euribor3m`: euribor 3 month rate - daily indicator (numeric)
- `nr.employed`: number of employees - quarterly indicator (numeric)

<br>

**Output variable (desired target)**
- `y` - apakah klien berlangganan deposit? (binary: "yes","no")

## Metode yang digunakan
Metode yang dilakukan pada penelitian ini adalah Random Forest yang merupakan ensemble model. Model dasarnya adalah Decision Trees. Random forest adalah salah satu model ensemble di mana kita membuat model dari decision tree, yang datanya merupakan hasil resample dari bootstrap dan tiap modelnya juga memiliki fitur yang random. Sehingga tiap modelnya tidak saling berkorelasi satu sama lainnya. Setelah dibuat modelnya, hasil prediksinya adalah hasil agregasi dari seluruh model yang sudah dibuat dengan mekanisme majority vote.

## Proses Eksperimentasi
Pada proses eksperimen, saya menggunakan cross validation untuk mendapatkan hyperparameter terbaik dari model. Hyperparameter yang dipakai adalah : Jumlah Max Features, Max Depth, Criterion dan N Extimators.

## Penjelasan Lebih Lengkap
Penjelasan lebih lengkap dapat dilihat pada laman berikut:
- easy report : https://medium.com/@helmysmp/memprediksi-client-berlangganan-deposit-dengan-data-telemarketing-menggunakan-random-forest-100bb4f4c875
- video presentasi : https://www.youtube.com/watch?v=6J4KjDh_LLA&ab_channel=HelmySatria
