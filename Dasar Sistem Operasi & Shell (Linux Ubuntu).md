🎯 Tujuan Akhir
- Menguasai perintah dasar terminal
- Memahami struktur direktori Linux
- Bisa menulis skrip shell sederhana
-Mengelola proses dan file dengan CLI

## 1.File & Folder Management
```
mkdir belajar_shell
cd belajar_shell
touch file1.txt file2.txt file3.txt
```
<img width="723" height="107" alt="image" src="https://github.com/user-attachments/assets/00a76ef8-a62e-467a-b4d5-c33d5a45cbbc" />

```
# Mencoba perintah manajemen file
mv file1.txt file1_renamed.txt       # rename file
```
<img width="738" height="53" alt="image" src="https://github.com/user-attachments/assets/8714cf39-039c-475b-888b-d563832b13a1" />


```
cp file2.txt file2_copy.txt          # copy file
```
<img width="737" height="57" alt="image" src="https://github.com/user-attachments/assets/aea2ed16-48cf-4be4-9fc8-2345489d6294" />


```
mkdir folder_tujuan
mv file3.txt folder_tujuan/          # pindahkan file ke folder
```

<img width="738" height="129" alt="image" src="https://github.com/user-attachments/assets/79ac8244-4842-402a-8ad4-db0ee4e00e62" />


```
rm file2_copy.txt                    # hapus file
rmdir folder_tujuan                  # hapus folder (harus kosong)
rm -r folder_tujuan                  # hapus folder (ketika ada isi folder)
```

<img width="734" height="23" alt="image" src="https://github.com/user-attachments/assets/997acacb-e13f-4d8c-bd59-031d37607a5b" />
<img width="737" height="57" alt="image" src="https://github.com/user-attachments/assets/aa7df976-258d-4516-ab91-b88088439275" />





## 2.Permission, User & Group
```
touch script.sh                           # create file
echo "#!/bin/bash" > script.sh            # mengisi text pada file (>) menimpa
echo "echo 'Hello World'" >> script.sh    # menambahkan text pada file (>>) menambahkan
```

<img width="724" height="202" alt="image" src="https://github.com/user-attachments/assets/85927e08-bdd0-48cf-acab-939ada30f5cf" />

```
# Mengubah permission
chmod +x script.sh          # menambahkan permission execute
ls -l script.sh             # melihat permission
chmod 755 script.sh         # mengatur permission rwxr-xr-x
```

<img width="729" height="163" alt="image" src="https://github.com/user-attachments/assets/998e2153-d15f-4e72-8731-36bb6cbc44d4" />

```
# Menjalankan script
./script.sh
```

<img width="730" height="58" alt="image" src="https://github.com/user-attachments/assets/974e116b-25d5-4d6c-a8f5-313687ae3f9d" />

```
# Melihat informasi user
id
whoami
```

<img width="727" height="109" alt="image" src="https://github.com/user-attachments/assets/ecceeab7-a3b3-4431-93c7-be0c1c14ae4f" />





## 3.Pengelolaan File Lanjut
```
# Membuat file teks dummy
echo "Ini adalah baris pertama" > dummy.txt
echo "Ini adalah baris kedua" >> dummy.txt
echo "Shell scripting itu menyenangkan" >> dummy.txt
echo "Linux adalah sistem operasi yang powerful" >> dummy.txt
```

<img width="860" height="360" alt="image" src="https://github.com/user-attachments/assets/6a8a81a3-5557-4880-a7c3-a215d9d1f56f" />

```
# Menggunakan perintah untuk melihat isi file
cat dummy.txt
head -n 2 dummy.txt     # menampilkan 2 baris pertama
tail -n 1 dummy.txt     # menampilkan 1 baris terakhir
less dummy.txt          # melihat isi file dengan navigasi
```

<img width="868" height="198" alt="image" src="https://github.com/user-attachments/assets/a977543e-0de9-43f7-86b8-9db81c8c7485" />
<img width="857" height="125" alt="image" src="https://github.com/user-attachments/assets/e3bd3952-b769-41c7-bf4e-72f56842488f" />

```
# Mencari kata dengan grep
grep "Shell" dummy.txt
```

<img width="856" height="52" alt="image" src="https://github.com/user-attachments/assets/94354560-7160-4be3-87e4-7524e21996c4" />

```
# Mencari file dengan find
find ~ -name "*.txt"    # mencari semua file .txt di home directory
```





##  4.Proses dan Sistem
```
# Memantau proses
ps aux                  # melihat semua proses
top                     # monitor proses interaktif (tekan q untuk keluar)
```

<img width="931" height="295" alt="image" src="https://github.com/user-attachments/assets/8e5983ee-d5de-4a49-8d44-2fbcb5844849" />
<img width="1850" height="317" alt="image" src="https://github.com/user-attachments/assets/d1949a7e-e8cc-4b98-a71e-a4b0182eee11" />

```
# Install htop jika belum ada
sudo apt install htop
htop                    # versi lebih baik dari top
```

<img width="1845" height="972" alt="image" src="https://github.com/user-attachments/assets/99ea97c8-dcde-41a5-bc16-fb02c621aaf1" />

```
# Membuat dan menghentikan proses
sleep 100 &             # menjalankan sleep di background
ps aux | grep sleep     # mencari PID proses sleep
kill [PID]              # ganti [PID] dengan angka PID yang ditemukan

# Menggunakan crontab
crontab -e              # edit jadwal cron
# Tambahkan baris berikut untuk menjalankan script setiap jam:
# 0 * * * * /path/to/script.sh
```





## 5.Variable, Alias, & Custom Terminal
```
# Mengecek variabel lingkungan
echo $HOME
echo $PATH
```
<img width="850" height="131" alt="image" src="https://github.com/user-attachments/assets/6cfa9878-7f5d-4d4c-aa7b-8d5c3b1572a6" />

```
# Membuat variabel dan alias
export NAMA="Belajar"
alias gs='git status'
alias cls='clear'
```

<img width="861" height="79" alt="image" src="https://github.com/user-attachments/assets/e69681f5-86e1-4dc1-8af4-2a3378e20e8b" />


```
# Menyimpan ke .bashrc
nano ~/.bashrc
# Tambahkan di bagian bawah file:
# export PROJECT=DevOps
# alias gs='git status'

# Memuat ulang .bashrc
source ~/.bashrc
```

<img width="855" height="170" alt="image" src="https://github.com/user-attachments/assets/941d6681-6e45-4aac-a40a-e555dfbabde7" />
<img width="856" height="43" alt="image" src="https://github.com/user-attachments/assets/24679382-b3f7-4a34-838f-b90572c83df5" />





## 6.Shell Scripting Dasar
1. Buat file sambutan.sh
   ```
   #!/bin/bash
   echo "Halo, siapa namamu?"
   read nama
   echo "Selamat datang, $nama!"
   ```
   
   <img width="493" height="136" alt="image" src="https://github.com/user-attachments/assets/c6a1c476-e143-497f-9cd3-c9cc1b5ec5bb" />

2. Buat file backup.sh untuk backup sederhana:
   ```
   #!/bin/bash
   # Skrip backup sederhana
   TIMESTAMP=$(date +"%Y%m%d_%H%M%S")
   BACKUP_DIR="/path/ke/backup/folder"
   SOURCE_DIR="/path/ke/sumber/folder"

   if [ ! -d "$BACKUP_DIR" ]; then
     mkdir -p "$BACKUP_DIR"
   fi

   cp -r "$SOURCE_DIR" "$BACKUP_DIR/backup_$TIMESTAMP"
   echo "Backup selesai pada $(date)" >> "$BACKUP_DIR/backup_log.txt"
   ```
3. Cara menjalankan script:
   ```
   chmod +x sambutan.sh backup.sh
   ./sambutan.sh
   ./backup.sh
   ```
   
   <img width="448" height="77" alt="image" src="https://github.com/user-attachments/assets/7721c774-698f-4056-8f50-4f7eab852b9e" />
