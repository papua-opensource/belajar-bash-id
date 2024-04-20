## Daftar Isi

1. [Operasi Dasar](#1-operasi-dasar)

    1.1. [Operasi File](#11-operasi-file)
    <br>
    1.2. [Operasi Teks](#12-operasi-teks)
    <br>
    1.3. [Operasi Direktori](#13-operasi-direktori)
    <br>
    1.4. [SSH, Informasi Sistem & Operasi Jaringan](#14-ssh-informasi-sistem--operasi-jaringan)
    <br>
    1.5. [Operasi Monitoring Proses](#15-operasi-monitoring-proses)

2. [Basic Shell Programming](#2-basic-shell-programming)

    2.1. [Variabel](#21-variabel)
    <br>
    2.2. [Array](#22-array)
    <br>
    2.3. [Substitusi String](#23-substitusi-string)
    <br>
    2.4. [Triks String Lainnya](#24-triks-string-lainnya)
    <br>
    2.5. [Fungsi](#25-fungsi)
    <br>
    2.6. [Pernyataan Kondisional](#26-pernyataan-kondisional)
    <br>
    2.7. [Pengulangan](#27-pengulangan)

3. [Trik](#3-trik)
4. [Debugging](#4-debugging)
5. [Multi-threading](#5-multi-threading)

# 1. Operasi Dasar

### a. `export`

Menampilkan semua variabel lingkungan (environment variable). Jika Anda ingin mendapatkan detail dari variabel tertentu, bisa mengunakan `echo $VARIABLE_NAME`.

```bash
export
```

Contoh:

```bash
$ export
AWS_HOME=/Users/kastau/.aws
LANG=en_US.UTF-8
LC_CTYPE=en_US.UTF-8
LESS=-R

$ echo $AWS_HOME
/Users/kastau/.aws
```

### b. `whatis`

whatis menampilkan deskripsi dari perintah yang diinputkan user atau pengguna, system calls, library functions, dan lainnya pada terminal.

```bash
whatis something
```

Example:

```bash
$ whatis bash
bash (1)             - GNU Bourne-Again SHell
```

### c. `whereis`

whereis digunakan untuk mencari executable file, source filesnya, dan ditampilkan di terminal menggunakan database yang dibuat oleh sistem secara otomatis.

```bash
whereis name
```

Example:

```bash
$ whereis php
/usr/bin/php
```

### d. `which`

which digunakan untuk mencari executable file yang ada di direktori tertentu yang sudah ditentukan sebelumnya oleh PATH environment variable. Perintah ini akan menampilkan `PATH` dari executable file yang ingin kamu cari.

```bash
which program_name
```

Example:

```bash
$ which php
/c/xampp/php/php
```

### e. clear

Menghapus isi dari console atau terminal.

## 1.1. Operasi File

<table>
   <tr>
      <td><a href="#a-cat">cat</a></td>
      <td><a href="#b-chmod">chmod</a></td>
      <td><a href="#c-chown">chown</a></td>
      <td><a href="#d-cp">cp</a></td>
      <td><a href="#e-diff">diff</a></td>
      <td><a href="#f-file">file</a></td>
      <td><a href="#g-find">find</a></td>
      <td><a href="#h-gunzip">gunzip</a></td>
      <td><a href="#i-gzcat">gzcat</a></td>
      <td><a href="#j-gzip">gzip</a></td>
      <td><a href="#k-head">head</a></td>
   </tr>
   <tr>
      <td><a href="#l-lpq">lpq</a></td>
      <td><a href="#m-lpr">lpr</a></td>
      <td><a href="#n-lprm">lprm</a></td>
      <td><a href="#o-ls">ls</a></td>
      <td><a href="#p-more">more</a></td>
      <td><a href="#q-mv">mv</a></td>
      <td><a href="#r-rm">rm</a></td>
      <td><a href="#s-tail">tail</a></td>
      <td><a href="#t-touch">touch</a></td>
   </tr>
</table>

### a. `cat`

It can be used for the following purposes under UNIX or Linux.

* Display text files on screen
* Copy text files
* Combine text files
* Create new text files

```bash
cat filename
cat file1 file2
cat file1 file2 > newcombinedfile
cat < file1 > file2 #copy file1 to file2 file1 > file2 #copy file1 to file2
```

### b. `chmod`

Perintah atau command chmod adalah singkatan dari "change mode" yang memungkinkan Kita untuk mengubah izin `read`, `write`, dan `execute` pada file dan folder. Untuk informasi lebih lanjut tentang perintah ini, kunjungi tautan berikut [Link](https://ss64.com/bash/chmod.html).

```bash
chmod -options filename
```

### c. `chown`

Perintah chown yang merupakan singkatan dari "change owner", memungkinkan Kita untuk mengubah pemilik atau owner dari file atau folder, yang mana dapat berupa user atau group. Kombinasi penggunaannya yaitu user (owner), kemudian groupnya, yang dipisahkan oleh titik dua `(:)`.

```bash
chown -options user:group filename
```

### d. `cp`

Copies a file from one location to other.

```bash
cp filename1 filename2
```

Dimana `filename1` adalah file sumbernya dan `filename2` adalah file destinasinya.

### e. `diff`

Compares files, and lists their differences.

```bash
diff filename1 filename2
```

### f. `file`

Determine file type.

```bash
file filename
```

Example:

```bash
$ file index.html
 index.html: HTML document, ASCII text
```

### g. `find`

Menemukan suatu file dalam direktori tertentu.

```bash
find directory options pattern
```

Example:

```bash
find . -name README.md
find /home/user1 -name '*.png'
```

### h. `gunzip`

Un-compresses files compressed by gzip.

```bash
gunzip filename
```

### i. `gzcat`

Lets you look at gzipped file without actually having to gunzip it.

```bash
gzcat filename
```

### j. `gzip`

Compresses files.

```bash
gzip filename
```

### k. `head`

Outputs the first 10 lines of file

```bash
head filename
```

### l. `lpq`

Check out the printer queue.

```bash
lpq
```

Example:

```bash
$ lpq
Rank    Owner   Job     File(s)                         Total Size
active  adnanad 59      demo                            399360 bytes
1st     adnanad 60      (stdin)                         0 bytes
```

### m. `lpr`

Print the file.

```bash
lpr filename
```

### n. `lprm`

Remove something from the printer queue.

```bash
lprm jobnumber
```

### o. `ls`

Lists your files. `ls` has many options: `-l` lists files in 'long format', which contains the exact size of the file, who owns the file, who has the right to look at it, and when it was last modified. `-a` lists all files, including hidden files. For more information on this command check this [link](https://ss64.com/bash/ls.html).

```bash
ls option
```

Example:
<pre>
$ ls -la
rwxr-xr-x   33 adnan  staff    1122 Mar 27 18:44 .
drwxrwxrwx  60 adnan  staff    2040 Mar 21 15:06 ..
-rw-r--r--@  1 adnan  staff   14340 Mar 23 15:05 .DS_Store
-rw-r--r--   1 adnan  staff     157 Mar 25 18:08 .bumpversion.cfg
-rw-r--r--   1 adnan  staff    6515 Mar 25 18:08 .config.ini
-rw-r--r--   1 adnan  staff    5805 Mar 27 18:44 .config.override.ini
drwxr-xr-x  17 adnan  staff     578 Mar 27 23:36 .git
-rwxr-xr-x   1 adnan  staff    2702 Mar 25 18:08 .gitignore
</pre>

### p. `more`

Shows the first part of a file (move with space and type q to quit).

```bash
more filename
```

### q. `mv`

Moves a file from one location to other.

```bash
mv filename1 filename2
```

Yang mana `filename1` adalah file sumbernya `filename2` adalah destinasinya.

Juga digunakan untuk mengganti nama atau rename file.

```bash
mv old_name new_name
```

### r. `rm`

Digunakan untuk menghapus file. Akan error jika command ini digunakan untuk menghapus direktori.
`rm: directory: is a directory`
Untuk menghapus direktori cukup tambahkan argumen `-r` sehingga akan menghapus isi direktori secara rekursif. Opsi lainnya yaitu jika ingin  mengahapus file atau direktori tanpa konfirmasi terlebih dahulu gunakan argumen `-f`.

```bash
rm filename
```

### s. `tail`

Outputs the last 10 lines of file. Use `-f` to output appended data as the file grows.

```bash
tail filename
```

### t. `touch`

Memperbarui akses dan time stamps dari file. Kita juga bisa memanfaatkan touch untuk membuat file baru.

```bash
touch filename
```

Example:

```bash
touch trick.md
```

## 1.2. Operasi Teks

<table>
    <tr>
      <td><a href="#a-awk">awk</a></td>
      <td><a href="#b-cut">cut</a></td>
      <td><a href="#c-echo">echo</a></td>
      <td><a href="#d-egrep">egrep</a></td>
      <td><a href="#e-fgrep">fgrep</a></td>
      <td><a href="#f-fmt">fmt</a></td>
      <td><a href="#g-grep">grep</a></td>
      <td><a href="#h-nl">nl</a></td>
      <td><a href="#i-sed">sed</a></td>
      <td><a href="#j-sort">sort</a></td>
   </tr>
   <tr>
      <td><a href="#k-tr">tr</a></td>
      <td><a href="#l-uniq">uniq</a></td>
      <td><a href="#m-wc">wc</a></td>
   </tr>
</table>

### a. `awk`

awk adalah perintah yang sangat berguna dalam menangani file teks. Beroperasi pada file baris per baris. Secara default menggunakan spasi untuk  memisahkan bidang-bidangnya. Berikut ini sintaks-sintaks yang umum digunakan

```bash
awk '/search_pattern/ { action_to_take_if_pattern_matches; }' file_to_parse
```

Mari kita ambil contoh dari file berikut `/etc/passwd`. Berikut data ada:

```
root:x:0:0:root:/root:/usr/bin/zsh
daemon:x:1:1:daemon:/usr/sbin:/usr/sbin/nologin
bin:x:2:2:bin:/bin:/usr/sbin/nologin
sys:x:3:3:sys:/dev:/usr/sbin/nologin
sync:x:4:65534:sync:/bin:/bin/sync
```

Sekarang coba kita dapatkan usernamenya saja dari file tadi. Dimana `-F` menentukan basis mana yang dipisahkan. dalam kasus ini `:`. `{ print $1 }`artinya mencetak bidang pertama yang cocok.

```bash
awk -F':' '{ print $1 }' /etc/passwd
```

Setelah menjalankan perintah tersebut dalam menghasilkan output atau keluaran seperti berikut.

```
root
daemon
bin
sys
sync
```

Untuk informasi lebih lanjut mengenai penggunaan `awk`, cek link berikut [link](https://www.cyberciti.biz/faq/bash-scripting-using-awk).

### b. `cut`

Hapus bagian tertentu dari baris teks tertentu

*example.txt*

```bash
red riding hood went to the park to play
```

*tunjukkan kolom 2 , 7 , dan 9 dengan spasi sebagai pemisah*

```bash
cut -d " " -f2,7,9 example.txt
```

```bash
riding park play
```

### c. `echo`

Menampilkan setiap baris dalam teks

*tampilkan "Hello World"*

```bash
echo Hello World
```

```bash
Hello World
```

*tampilkan "Hello World" dengan baris baru di antara kata-kata (enter)*

```bash
echo -ne "Hello\nWorld\n"
```

```bash
Hello
World
```

### d. `egrep`

Mencetak baris dengan pola yang diinginkan  - Extended Expression (alias for: 'grep -E')

*example.txt*

```bash
Lorem ipsum
dolor sit amet,
consetetur
sadipscing elitr,
sed diam nonumy
eirmod tempor
invidunt ut labore
et dolore magna
aliquyam erat, sed
diam voluptua. At
vero eos et
accusam et justo
duo dolores et ea
rebum. Stet clita
kasd gubergren,
no sea takimata
sanctus est Lorem
ipsum dolor sit
amet.
```

*tampilkan baris yang memiliki "Lorem" or "dolor" di dalamnya.*

```bash
egrep '(Lorem|dolor)' example.txt
or
grep -E '(Lorem|dolor)' example.txt
```

```bash
Lorem ipsum
dolor sit amet,
et dolore magna
duo dolores et ea
sanctus est Lorem
ipsum dolor sit
```

### e. `fgrep`

Mencetak baris yang cocok dengan pola - FIXED pattern matching  (alias for: 'grep -F')

*example.txt*

```bash
Lorem ipsum
dolor sit amet,
consetetur
sadipscing elitr,
sed diam nonumy
eirmod tempor
foo (Lorem|dolor)
invidunt ut labore
et dolore magna
aliquyam erat, sed
diam voluptua. At
vero eos et
accusam et justo
duo dolores et ea
rebum. Stet clita
kasd gubergren,
no sea takimata
sanctus est Lorem
ipsum dolor sit
amet.
```

*Menemukan string yang tepat '(Lorem|dolor)' in example.txt*

```bash
fgrep '(Lorem|dolor)' example.txt
or
grep -F '(Lorem|dolor)' example.txt
```

```bash
foo (Lorem|dolor)
```

### f. `fmt`

Format teks dengan simpel

*example: example.txt (1 line)*

```bash
Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua. At vero eos et accusam et justo duo dolores et ea rebum. Stet clita kasd gubergren, no sea takimata sanctus est Lorem ipsum dolor sit amet.
```

*keluaran example.txt hingga 20 baris*

```bash
cat example.txt | fmt -w 20
```

```bash
Lorem ipsum
dolor sit amet,
consetetur
sadipscing elitr,
sed diam nonumy
eirmod tempor
invidunt ut labore
et dolore magna
aliquyam erat, sed
diam voluptua. At
vero eos et
accusam et justo
duo dolores et ea
rebum. Stet clita
kasd gubergren,
no sea takimata
sanctus est Lorem
ipsum dolor sit
amet.
```

### g. `grep`

Looks for text inside files. You can use grep to search for lines of text that match one or many regular expressions, and outputs only the matching lines.

```bash
grep pola namafile
```

Contoh:

```bash
$ grep admin /etc/passwd
_kadmin_admin:*:218:-2:Kerberos Admin Service:/var/empty:/usr/bin/false
_kadmin_changepw:*:219:-2:Kerberos Change Password Service:/var/empty:/usr/bin/false
_krb_kadmin:*:231:-2:Open Directory Kerberos Admin Service:/var/empty:/usr/bin/false
```

Anda juga dapat memaksa grep untuk mengabaikan huruf besar/kecil dengan menggunakan opsi `-i`. `-r` dapat digunakan untuk mencari semua file didalam direktori tertentu, contohnya:

```bash
grep -r admin /etc/
```

Dan `-w` untuk mencari kata saja. Untuk detail lebih lanjut tentang `grep`, silahkan kunjungi [link] berikut (<https://www.cyberciti.biz/faq/grep-in-bash>).

### h. `nl`

Menghitung jumlah baris dari sebuah file teks

*example.txt*

```bash
Lorem ipsum
dolor sit amet,
consetetur
sadipscing elitr,
sed diam nonumy
eirmod tempor
invidunt ut labore
et dolore magna
aliquyam erat, sed
diam voluptua. At
vero eos et
accusam et justo
duo dolores et ea
rebum. Stet clita
kasd gubergren,
no sea takimata
sanctus est Lorem
ipsum dolor sit
amet.
```

*tampilkan example.txt dengan nomor barisnya*

```bash
nl -s". " example.txt
```

```bash
     1. Lorem ipsum
     2. dolor sit amet,
     3. consetetur
     4. sadipscing elitr,
     5. sed diam nonumy
     6. eirmod tempor
     7. invidunt ut labore
     8. et dolore magna
     9. aliquyam erat, sed
    10. diam voluptua. At
    11. vero eos et
    12. accusam et justo
    13. duo dolores et ea
    14. rebum. Stet clita
    15. kasd gubergren,
    16. no sea takimata
    17. sanctus est Lorem
    18. ipsum dolor sit
    19. amet.
```

### i. `sed`

Sed atau kepanjangannya `Stream editor` biasas digunakan untuk memfilter dan mengubah teks

*example.txt*

```bash
Hello This is a Test 1 2 3 4
```

*ganti semua spasi dengan tanda hubung*

```bash
sed 's/ /-/g' example.txt
```

```bash
Hello-This-is-a-Test-1-2-3-4
```

*ganti semua digit/angka dengan "d"*

```bash
sed 's/[0-9]/d/g' example.txt
```

```bash
Hello This is a Test d d d d
```

### j. `sort`

Mengurutkan baris file teks

*example.txt*

```bash
f
b
c
g
a
e
d
```

*mengurutkan example.txt*

```bash
sort example.txt
```

```bash
a
b
c
d
e
f
g
```

*mengacak yang sebelumnya sudah disort example.txt*

```bash
sort example.txt | sort -R
```

```bash
b
f
a
c
d
g
e
```

### k. `tr`

Menerjemahkan atau menghapus karakter.

*example.txt*

```bash
Hello World Foo Bar Baz!
```

*mengambil semua huruf kecil dan menjadikannya huruf kapital*

```bash
cat example.txt | tr 'a-z' 'A-Z'
```

```bash
HELLO WORLD FOO BAR BAZ!
```

*mengganti semua spasi dengan menjadikannya sebagai baris baru*

```bash
cat example.txt | tr ' ' '\n'
```

```bash
Hello
World
Foo
Bar
Baz!
```

### l. `uniq`

Laporkan atau hilangkan baris yang berulang

*example.txt*

```bash
a
a
b
a
b
c
d
c
```

*tampilkan hanya baris-baris unik dari example.txt (pertama-tama Anda harus mengurutkannya, jika tidak maka tidak akan terlihat tumpang tindih)*

```bash
sort example.txt | uniq
```

```bash
a
b
c
d
```

*tampilkan item unik untuk setiap baris, dan beri tahu saya berapa banyak contoh yang ditemukan*

```bash
sort example.txt | uniq -c
```

```bash
    3 a
    2 b
    2 c
    1 d
```

### m. `wc`

Tells you how many lines, words and characters there are in a file.

```bash
wc filename
```

Contoh:

```bash
$ wc demo.txt
7459   15915  398400 demo.txt
```

Di mana `7459` adalah jumlah baris, `15915` adalah jumlah kata, dan `398400` adalah jumlah karakter.

## 1.3. Operasi Direktori

<table>
   <tr>
      <td><a href="#a-cd">cd</a></td>
      <td><a href="#b-mkdir">mkdir</a></td>
      <td><a href="#c-pwd">pwd</a></td>
   </tr>
</table>

### a. `cd`

Moves you from one directory to other. Running this

```bash
cd
```

memindahkan Anda ke direktori home. Perintah ini menerima sebuah `dirname` opsional, yang akan memindahkan Anda ke direktori tersebut.

```bash
cd dirname
```

### b. `mkdir`

Makes a new directory.

```bash
mkdir dirname
```

Anda dapat menggunakan ini untuk membuat beberapa direktori sekaligus di dalam direktori Anda saat ini.

```bash
mkdir 1stDirectory 2ndDirectory 3rdDirectory
```

You can also use this to create parent directories at the same time with the -p (or --parents) flag. For instance, if you wanted a directory named 'project1' in another subdirectory at '/samples/bash/projects/', you could run:

```bash
mkdir -p /samples/bash/projects/project1
mkdir --parents /samples/bash/projects/project1
```

Kedua perintah di atas akan melakukan hal yang sama.
Jika salah satu direktori ini belum ada, maka direktori tersebut akan dibuat juga.

### c. `pwd`

Tells you which directory you currently are in.

```bash
pwd
```

## 1.4. SSH, Informasi Sistem & Operasi Jaringan

<table>
   <tr>
      <td><a href="#a-bg">bg</a></td>
      <td><a href="#b-cal">cal</a></td>
      <td><a href="#c-date">date</a></td>
      <td><a href="#d-df">df</a></td>
      <td><a href="#e-dig">dig</a></td>
      <td><a href="#f-du">du</a></td>
      <td><a href="#g-fg">fg</a></td>
      <td><a href="#h-finger">finger</a></td>
      <td><a href="#i-jobs">jobs</a></td>
      <td><a href="#j-last">last</a></td>
   </tr>
   <tr>
      <td><a href="#k-man">man</a></td>
      <td><a href="#l-passwd">passwd</a></td>
      <td><a href="#m-ping">ping</a></td>
      <td><a href="#n-ps">ps</a></td>
      <td><a href="#o-quota">quota</a></td>
      <td><a href="#p-scp">scp</a></td>
      <td><a href="#q-ssh">ssh</a></td>
      <td><a href="#r-top">top</a></td>
      <td><a href="#s-uname">uname</a></td>
      <td><a href="#t-uptime">uptime</a></td>
   </tr>
   <tr>
      <td><a href="#u-w">w</a></td>
      <td><a href="#v-wget">wget</a></td>
      <td><a href="#w-whoami">whoami</a></td>
      <td><a href="#x-whois">whois</a></td>
      <td><a href="#y-rsync">sync</a></td>
      <td><a href="#z-curl">curl</a></td>
   </tr>
</table>

### a. `bg`

Melihat daftar pekerjaan (jobs) yang dihentikan atau proses yang berjalan dilatar belakang (background); melanjutkan pekerjaan yang dihentikan di latar belakang.

### b. `cal`

Menampilkan kalender dalam format bulan.

### c. `date`

Menampilkan tanggal dan waktu saat ini.

### d. `df`

Menunjukkan penggunaan disk.

### e. `dig`

Gets DNS information for domain.

```bash
dig domain
```

### f. `du`

Menunjukkan penggunaan disk dari file atau direktori. Untuk informasi lebih lanjut mengenai perintah ini, lihat [link] ini (<http://www.linfo.org/du.html>).

```bash
du [option] [filename|directory]
```

Options:
* `-h` (human readable) Displays output it in kilobytes (K), megabytes (M) and gigabytes (G).
* `-s` (supress or summarize) Outputs total disk space of a directory and supresses reports for subdirectories.

Example:

```bash
du -sh pictures
1.4M pictures
```

### g. `fg`

Menampilkan pekerjaan terbaru di latar depan (foreground).

### h. `finger`

Displays information about user.

```bash
finger username
```

### i. `jobs`

Mencantumkan pekerjaan yang berjalan di latar belakang, dengan memberikan penomoran pada pekerjaan itu.

### j. `last`

Lists your last logins of specified user.

```bash
last yourUsername
```

### k. `man`

Shows the manual for specified command.

```bash
man command
```

### l. `passwd`

Memungkinkan pengguna yang masuk saat ini untuk mengubah kata sandi mereka (password).

### m. `ping`

Pings host and outputs results.

```bash
ping host
```

### n. `ps`

Lists your processes.

```bash
ps -u yourusername
```

Use the flags ef. e for every process and f for full listing.

```bash
ps -ef
```

### o. `quota`

Shows what your disk quota is.

```bash
quota -v
```

### p. `scp`

Mentransfer file antara host lokal dan host jarak jauh atau antara dua host jarak jauh (remote host).

*menyalin dari host lokal ke host jarak jauh (remote host)*

```bash
scp source_file user@host:directory/target_file
```

*menyalin dari host jarak jauh ke host lokal*

```bash
scp user@host:directory/source_file target_file
scp -r user@host:directory/source_folder target_folder
```

This command also accepts an option `-P` that can be used to connect to specific port.

```bash
scp -P port user@host:directory/source_file target_file
```

### q. `ssh`

ssh (SSH client) is a program for logging into and executing commands on a remote machine.

```bash
ssh user@host
```

This command also accepts an option `-p` that can be used to connect to specific port.

```bash
ssh -p port user@host
```

### r. `top`

Menampilkan proses Anda yang sedang aktif.

### s. `uname`

Shows kernel information.

```bash
uname -a
```

### t. `uptime`

Menunjukkan waktu aktif saat ini.

### u. `w`

Menampilkan siapa yang sedang online.

### v. `wget`

Downloads file.

```bash
wget file
```

### w. `whoami`

Menampilkan nama pengguna yang kita pakai saat ini.

### x. `whois`

Gets whois information for domain.

```bash
whois domain
```

### y. `rsync`

Melakukan pekerjaan yang sama persis dengan perintah `scp`, tetapi hanya mentransfer file yang diubah. Berguna saat mentransfer folder yang sama ke/dari server beberapa kali.

```bash
rsync source_folder user@host:target_folder
rsync user@host:target_folder target_folder
```

### z. `curl`

Curl adalah alat bantu untuk meminta atau mengirim data menggunakan sintaks URL. Berguna pada sistem di mana Anda hanya memiliki terminal yang tersedia untuk membuat berbagai permintaan.

```bash
curl url
```

Use  `-X` or `--request` to specify which method you would like invoke (GET, POST, DELETE, ...).
Use `-d <data>` or `--data <data>` to POST data on given URL.

## 1.5. Operasi Pemantauan Proses

<table>
   <tr>
      <td><a href="#a-kill">kill</a></td>
      <td><a href="#b-killall">killall</a></td>
      <td><a href="#c-&">&amp;</a></td>
      <td><a href="#d-nohup">nohup</a></td>
   </tr>
</table>

### a. `kill`

Kills (ends) the processes with the ID you gave.

```bash
kill PID
```

### b. `killall`

Kill all processes with the name.

```bash
killall namaproses
```

### c. &

Simbol `&` menginstruksikan perintah untuk dijalankan sebagai proses latar belakang (background) dalam subshell.

```bash
command &
```

### d. `nohup`

nohup adalah singkatan dari "No Hang Up". Ini memungkinkan untuk menjalankan perintah/proses atau skrip shell yang dapat terus berjalan di latar belakang setelah Anda keluar dari shell.

```bash
nohup command
```

Combine it with `&` to create background processes

```bash
nohup command &
```

# 2. Dasar-Dasar Pemrogramana Shell

Baris pertama yang akan Anda tulis dalam file skrip bash disebut `shebang`. Baris ini dalam skrip apa pun menentukan kemampuan skrip untuk dieksekusi seperti eksekusi mandiri tanpa mengetikkan sh, bash, python, php, dan lain-lain terlebih dahulu di terminal.

```bash
#!/usr/bin/env bash
```

## 2.1. Variabel

Membuat variabel dalam bash mirip dengan bahasa lain. Tidak ada tipe data. Variabel dalam bash dapat berisi angka, karakter, string karakter, dll. Anda tidak perlu mendeklarasikan variabel, cukup dengan memberikan nilai pada referensinya saja sudah cukup untuk membuatnya.

Contoh:

```bash
str="hello world"
```

Baris di atas membuat variabel `str` dan menetapkan "hello world" ke variabel tersebut. Nilai variabel diambil dengan meletakkan `$` di awal nama variabel.

Contoh:

```bash
echo $str   # hello world
```

## 2.2. Array

Seperti bahasa lain, bash juga memiliki array. Sebuah array adalah sebuah variabel yang berisi banyak nilai. Tidak ada batasan maksimum pada ukuran array. Array dalam bash berbasis nol. Elemen pertama diindeks dengan elemen 0. Ada beberapa cara untuk membuat array di bash yang diberikan di bawah ini.

Contoh:

```bash
array[0]=val
array[1]=val
array[2]=val
array=([2]=val [0]=val [1]=val)
array=(val val val)
```

Untuk menampilkan nilai pada indeks tertentu, gunakan sintaks berikut:

```bash
${array[i]}     # dimana i adalah indeksnya
```

Jika tidak ada indeks yang diberikan, elemen larik 0 diasumsikan. Untuk mengetahui berapa banyak nilai yang ada dalam larik, gunakan sintaks berikut:

```bash
${#array[@]}
```

Bash juga mendukung kondisi terner. Lihat beberapa contoh di bawah ini.

```bash
${varname:-word}    # if varname exists and isn't null, return its value; otherwise return word
${varname:=word}    # if varname exists and isn't null, return its value; otherwise set it word and then return its value
${varname:+word}    # if varname exists and isn't null, return word; otherwise return null
${varname:offset:length}    # performs substring expansion. It returns the substring of $varname starting at offset and up to length characters
```

## 2.3 Substitusi String

Periksa beberapa sintaks tentang cara memanipulasi string

```bash
${variabel#pola}         # jika pola cocok dengan awal nilai variabel, hapus bagian terpendek yang cocok dan kembalikan sisanya
${variabel#pola}        # jika pola cocok dengan awal nilai variabel, hapus bagian terpanjang yang cocok dan kembalikan sisanya
${variabel%pola}         # jika pola cocok dengan akhir nilai variabel, hapus bagian terpendek yang cocok dan kembalikan sisanya
${variabel%%pola}        # jika pola cocok dengan akhir nilai variabel, hapus bagian terpanjang yang cocok dan kembalikan sisanya
${variabel/pola/string}  # kecocokan terpanjang dengan pola dalam variabel diganti dengan string. Hanya kecocokan pertama yang diganti
${variabel//pola/string} # kecocokan terpanjang dengan pola dalam variabel diganti dengan string. Semua kecocokan diganti
${#varname}     # mengembalikan panjang nilai variabel sebagai string karakter
```

## 2.4. Trik String Lainnya

Bash memiliki beberapa trik singkatan untuk melakukan berbagai hal pada string.

```bash
${variabel ,,}    #ini mengubah setiap huruf dalam variabel menjadi huruf kecil
${variabel^^}    #ini mengubah setiap huruf dalam variabel menjadi huruf besar

${variabel:2:8}  #ini mengembalikan substring dari sebuah string, dimulai dari karakter pada indeks ke-2 (string dimulai dari indeks 0, jadi ini adalah karakter ke-3),
                 #Substring akan memiliki panjang 8 karakter, jadi ini akan mengembalikan string yang terdiri dari karakter ke-3 hingga ke-11.
```

Berikut ini beberapa trik pencocokan pola yang praktis

```bash
if [ [ "$variabel" == *subString* ]]  #ini mengembalikan nilai true jika substring yang diberikan ada di dalam variabel
if [[ "$variabel" != *subString* ]]  #ini mengembalikan nilai true jika substring yang diberikan tidak ada di dalam variabel
if [[ "$variabel" == subString* ]]   #ini mengembalikan nilai true jika variabel dimulai dengan subString yang diberikan
if [[ "$variabel" == *subString ]]   #ini mengembalikan nilai true jika variabel diakhiri dengan subString yang diberikan
```

Hal di atas dapat dipersingkat dengan menggunakan pernyataan kasus dan kata kunci IN

```bash
case "$var" in
 begin*)
  #variabel dimulai dengan "begin"
 ;;
 *subString*)
  #subString ada di dalam variabel
 ;;

 * subSubString lainnya*)
  #subString lainnya ada di dalam variabel
 ;;
esac
```

## 2.5. Fungsi

Seperti pada hampir semua bahasa pemrograman, Anda dapat menggunakan fungsi untuk mengelompokkan potongan-potongan kode dengan cara yang lebih logis atau mempraktikkan seni rekursi. Mendeklarasikan sebuah fungsi hanyalah masalah menulis fungsi my_func { my_code }. Memanggil sebuah fungsi sama seperti memanggil program lain, Anda cukup menuliskan namanya.

```bash
nama fungsi() {
    perintah shell
}
```

Contoh:

```bash
#!/bin/bash
function hello {
   echo world!
}
hello

function say {
    echo $1
}
say "hello world!"
```

Ketika Anda menjalankan contoh di atas, fungsi `hello` akan mengeluarkan output "world!". Kedua fungsi di atas, `hello` dan `say`, adalah sama. Perbedaan utamanya adalah fungsi `say`. Fungsi ini, mencetak argumen pertama yang diterimanya. Argumen, di dalam fungsi, diperlakukan dengan cara yang sama seperti argumen yang diberikan ke skrip.

## 2.6. Kondisi

Pernyataan kondisional dalam bash mirip dengan bahasa pemrograman lainnya. Kondisi memiliki banyak bentuk seperti bentuk yang paling dasar adalah pernyataan `if` ekspresi `then` di mana pernyataan hanya dieksekusi jika ekspresi bernilai true.

```bash
if [ ekspresi]; then
    akan dieksekusi hanya jika ekspresi bernilai benar
else
    akan dieksekusi jika ekspresi bernilai salah
fi
```

Terkadang jika kondisi menjadi membingungkan, Anda dapat menulis kondisi yang sama menggunakan `pernyataan kasus`.

```bash
case expression in
    pola1 )
        statements ;;
    pola2 )
        statements ;;
    ...
esac
```

COntoh penggunaan ekspresi:

```bash
pernyataan1 && pernyataan2 # kedua pernyataan tersebut benar
pernyataan1 || pernyataan2 # setidaknya salah satu dari pernyataan bernilai benar

str1=str2 # str1 cocok dengan str2
str1!=str2 # str1 tidak cocok dengan str2
str1<str2 # str1 kurang dari str2
str1>str2 # str1 lebih besar dari str2
-n str1 # str1 tidak nol (memiliki panjang lebih besar dari 0)
-z str1 # str1 adalah null (memiliki panjang 0)

-a file # file ada
-d file # file ada dan merupakan sebuah direktori
-e file # file ada; sama dengan -a
-f file # file ada dan merupakan file biasa (yaitu, bukan direktori atau jenis file khusus lainnya)
-r file # Anda memiliki izin baca
-s berkas # berkas ada dan tidak kosong
-w file # Anda memiliki izin menulis
-x berkas # Anda memiliki izin eksekusi pada berkas, atau izin pencarian direktori jika berkas tersebut adalah sebuah direktori
-N file # file telah dimodifikasi sejak terakhir kali dibaca
-O file # file Anda sendiri
-G file # ID grup file cocok dengan ID grup Anda (atau salah satu ID grup Anda, jika Anda berada dalam beberapa grup)

file1 -nt file2 # file1 lebih baru dari file2
file1 -ot file2 # file1 lebih tua dari file2

-lt # kurang dari
-le # kurang dari atau sama dengan
-eq # sama dengan
-ge # lebih besar dari atau sama dengan
-gt # lebih besar dari
-ne # tidak sama
```

## 2.7. Perulangan

Ada tiga jenis perulangan dalam bash. `for`, `while` dan `until`.

`for` Sintaks:

```bash
for x := 1 to 10 do
mulai
  pernyataan
end

for nama [in list]
do
  pernyataan yang dapat menggunakan $nama
done

for (( inisialisasi ; kondisi akhir ; update ))
do
  pernyataan-pernyataan
done
```

`while` Sintaks:

```bash
while kondisi; do
  pernyataan
done
```

`until` Sintaks:

```bash
until kondisi; do
    pernyataan
done
```

# 3. Trik

## Tetapkan Nama Alias

Jalankan `nano ~/.bash_profile` lalu tambahkan baris berikut:

```bash
alias dockerlogin='ssh www-data@adnan.local -p2222'  # add your alias in .bash_profile
```

## Untuk membuka direktori tertentu dengan cepat

Jalankan `nano ~/.bashrc` dan tambahkan baris berikut:

```bash
export hotellogs="/workspace/hotel-api/storage/logs"
```

Sekarang Anda dapat menggunakan jalur yang disimpan di alias:

```bash
source ~/.bashrc
cd $hotellogs
```

## Jalankan kembali perintah sebelumnya

This goes back to the days before you could rely on keyboards to have an "up" arrow key, but can still be useful.
To run the last command in your history

```bash
!!
```

Kesalahan yang sering terjadi adalah lupa menggunakan `sudo` untuk mengawali perintah yang membutuhkan eksekusi khusus. Daripada mengetikkan seluruh perintah lagi, Anda dapat:

```bash
sudo !!
```

Ini akan mengubah `mkdir somedir` menjadi `sudo mkdir somedir`.

## Keluar dari perangkap

Jadikan skrip bash Anda lebih kuat dengan melakukan pembersihan secara andal.

```bash
function finish {
  # pembersihan Anda di sini. misal, bunuh semua proses bercabang
  jobs -p | xargs kill
}
trap finish EXIT
```

## Menyimpan Environment Variabel Anda

Ketika Anda melakukan `export FOO = BAR`, variabel Anda hanya diekspor dalam shell saat ini dan semua anak-anaknya, untuk mempertahankannya di masa depan, Anda cukup menambahkan perintah untuk mengekspor variabel Anda dalam berkas `~/.bash_profile`.

```bash
echo export FOO=BAR >> ~/.bash_profile
```

## Mengakses skrip Anda

Anda dapat dengan mudah mengakses skrip Anda dengan membuat folder bin di /home Anda dengan `mkdir ~/bin`, sekarang semua skrip yang Anda taruh di folder ini dapat Anda akses di direktori mana pun.

Jika Anda tidak dapat mengakses, coba tambahkan kode di bawah ini pada berkas `~/.bash_profile` Anda dan setelah melakukan `source ~/.bash_profile`.

```bash
# setel PATH agar menyertakan tempat sampah pribadi pengguna jika ada
if [ -d "$HOME/bin" ] ; then
    PATH="$HOME/bin:$PATH"
fi
```

# 4. Debugging

Anda dapat dengan mudah men-debug skrip bash dengan memberikan opsi yang berbeda pada perintah `bash`. Sebagai contoh `-n` tidak akan menjalankan perintah dan hanya memeriksa kesalahan sintaks. `-v` menggemakan perintah sebelum menjalankannya. Perintah echo `-x` setelah pemrosesan baris perintah.

```bash
bash -n scriptname
bash -v scriptname
bash -x scriptname
```

# 5. Multi-threading

Anda dapat dengan mudah melakukan multi-threading pekerjaan Anda dengan menggunakan `&`. Semua pekerjaan tersebut akan berjalan di latar belakang secara bersamaan dan Anda dapat melihat proses-proses di bawah ini berjalan menggunakan `jobs`.

```bash
sleep 15 & sleep 5 &
```

Perintah opsional `wait` kemudian akan menunggu sampai semua pekerjaan selesai.

```bash
sleep 10 & sleep 5 &
wait
```

## Kontribusi

* Silahkan membaca [panduan konribusi](CONTRIBUTING.md) sebelum menambahkan referensi atau terjemahan baru.
* Spread the word

## Referensi

Proyek ini mengambil referensi dari: [Idnan/bash-guide](https://github.com/Idnan/bash-guide)
