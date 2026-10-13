# Tugas-6

VI. Tugas
1. Eksekusi seluruh profile yang ada :
a. Edit file profile /etc/profile dan tampilkan pesan sebagai berikut :
echo “Profile dari /etc/profile”
<img width="714" height="482" alt="Screenshot From 2026-10-13 02-41-35" src="https://github.com/user-attachments/assets/e7e27acd-6e56-45d8-b66a-b769124325a3" />


b. Asumsi nama anda stD02001, maka edit semua profile yang ada yaitu :
/home/stD02001/.bash_profile
/home/. stD02001/.bash_login
/home/mahasiswa/.profile
/home/mahasiswa/.bashrc
Ganti nama /home/mahasiswa dengan nama anda sendiri. Pada setiap
file tersebut, cantumkan instruksi echo, misalnya pada /home/
mahasiswa/.bash_profile :
echo “Profile dari .bash_profile”
Lakukan hal yang sama untuk file lainnya, sesuaikan tampilan dengan nama file
yang bersangkutan.
<img width="714" height="482" alt="Screenshot From 2026-10-13 02-41-35" src="https://github.com/user-attachments/assets/1ef77694-3877-4891-8ae7-679a5b3a8727" />

c. Jalankan instruksi subtitute user, kemudian keluar dengan perintah exit sebagai
berikut:
$ su mahasiswa
$ exit
kemudian gunakan opsi – sebagai berikut :
$ su – mahasiswa
$ exit
Jelaskan perbedaan kedua utilitas tersebut.
<img width="714" height="482" alt="Screenshot From 2026-10-13 02-55-34" src="https://github.com/user-attachments/assets/0314bc0c-3efb-438f-b90a-f68a88e1b446" />


2. Prompt String (PS)
a. Edit file .bash_profile, ganti prompt PS1 dengan ‘>’. Instruksi export diperlukan
dengan parameter nama variable tersebut, agar perubahan variable PS1 dikenal
oleh semua shell
PS1=’> ‘
export PS1
<img width="714" height="507" alt="Screenshot From 2026-10-13 03-06-21" src="https://github.com/user-attachments/assets/a10a04c9-6faf-4ee3-ba89-795cb3ec621b" />


b. Eksperimen hasil PS1 :
$ PS1=“\! > “
69 > PS1=”\d > “
Mon Sep 23 > PS1=”\t > “
10:10:20 > PS1=”Saya=\u > “
Saya=mahasiswa > PS1=”\w >”
~ > PS1=\h >”
<img width="714" height="507" alt="Screenshot From 2026-10-13 03-06-21" src="https://github.com/user-attachments/assets/2061999b-f63b-4cad-a569-565f70ef0167" />


3. Logout
Edit file .bash_logout, tampilkan pesan dan tahan selama 5 detik, sebelum eksekusi
logout
Echo “Terima kasih atas sesi yang diberikan”
Sleep 5
clear
<img width="714" height="507" alt="Screenshot From 2026-10-13 03-15-45" src="https://github.com/user-attachments/assets/9866630a-1ff6-4245-ac60-f149e1b5422d" />


4. Bash script
a. Buat 3 buah script p1.sh, p2.sh, p3.sh dengan isi masing-masing :
p1.sh
#! /bin/bash
echo “Program p1” ls –l
<img width="714" height="835" alt="image" src="https://github.com/user-attachments/assets/f19c04e0-0278-43b2-ba28-3b33fd3b4d23" />

p2.sh
#! /bin/bash
echo “Program p2” who
<img width="714" height="835" alt="image" src="https://github.com/user-attachments/assets/ad74232e-b37a-4670-876f-b8de85e6b74e" />


p3.sh
#! /bin/bash
echo “Program p3” ps x
<img width="714" height="835" alt="image" src="https://github.com/user-attachments/assets/ccb3addb-cb9a-4a03-bc5c-0e40c742526b" />


b. Jalankan script tersebut sebagai berikut :
$ ./p1.sh ; ./p3.sh ; ./p2.sh
$ ./p1.sh &
$ ./p1.sh $ ./p2.sh & ./p3.sh &
$ ./p1.sh ; ./p3.sh ) &
<img width="714" height="835" alt="Screenshot From 2026-10-13 03-24-48" src="https://github.com/user-attachments/assets/61bf6d9c-cbf6-4733-8b24-3456dcb273c9" />
<img width="714" height="835" alt="Screenshot From 2026-10-13 03-27-58" src="https://github.com/user-attachments/assets/920747db-1274-418e-acb4-2f08f537cc7a" />


5. Jobs
a. Buat shell-script yang melakukan loop dengan nama pwaktu.sh, setiap 10 detik,
kemudian menyimpan tanggal dan jam pada file hasil.
#!/bin/bash
while [ true ]
do
date >> hasil
sleep 10
done
<img width="714" height="835" alt="Screenshot From 2026-10-13 03-32-35" src="https://github.com/user-attachments/assets/5a32295c-65f7-412a-a97d-27241c82ce46" />


b. Jalankan sebagai background; kemudian jalankan satu program (utilitas find) di
background sebagai berikut :
$ jobs
$ find / -print > files 2>/dev/null &
$ jobs
<img width="714" height="835" alt="Screenshot From 2026-10-13 03-37-53" src="https://github.com/user-attachments/assets/bdc3750b-a59e-4b4c-82bc-d62b494ce50c" />


c. Jadikan program ke 1 sebagai foreground, tekan ^Z dan kembalikan program
tersebut ke background
$ fg %1
$ bg
<img width="714" height="835" alt="Screenshot From 2026-10-13 03-41-24" src="https://github.com/user-attachments/assets/a7a73c0a-160c-4b7f-9b35-cdfb4e694d34" />

d. Stop program background dengan utilitas kill
$ ps x
$ kill [Nomor PID]
<img width="714" height="835" alt="Screenshot From 2026-10-13 03-52-33" src="https://github.com/user-attachments/assets/c7dfb618-d24c-4888-98ca-7a3ba1f6dc54" />


7. History
a. Ganti nilai HISTSIZE dari 1000 menjadi 20
$ HISTSIZE=20
$ h
<img width="714" height="835" alt="Screenshot From 2026-10-13 03-55-27" src="https://github.com/user-attachments/assets/06a4af52-cd1a-4f47-bf0f-b65a3dd88dd2" />


b. Gunakan fasilitas history dengan mengedit instruksi baris ke 5 dari instruksi yang
terakhir dilakukan
$ !-5
<img width="714" height="835" alt="Screenshot From 2026-10-13 03-56-39" src="https://github.com/user-attachments/assets/56bfa2fb-27ac-4f75-a5d1-4e1694b4e893" />


c. Ulangi instruksi yang terakhir. Gunakan juga ^P dan ^N untuk bernavigasi pada
history bufer
$ !!
<img width="714" height="835" alt="Screenshot From 2026-10-13 03-58-23" src="https://github.com/user-attachments/assets/91af72b1-6f69-467f-962b-136e9288d56b" />


d. Ulangi instruksi pada history bufer nomor 150
$ !150
<img width="714" height="835" alt="Screenshot From 2026-10-13 03-59-45" src="https://github.com/user-attachments/assets/c8840260-831c-4475-843c-0faba46c89f0" />


e. Ulangi instruksi dengan prefix “ls”
$ !ls
<img width="714" height="835" alt="Screenshot From 2026-10-13 04-00-13" src="https://github.com/user-attachments/assets/00a77db6-0b76-483a-bd32-09d9f76596af" />
