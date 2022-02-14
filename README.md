# OSSEC-HIDS
OSSEC (Open Source HIDS SECurity) merupakan salah satu tools profesional kemanan cyber, dimana tools ini digunakan sebagai HIDS. HIDS sendiri memiliki kepanjangan (Host Intrusion Detection System), dimana tools ini melakukan monitoring dan melaporkan kejadian/intrusi pada suatu perangkat host. selain HIDS OSSEC ada juga tools HIDS tripwire, keduanya memiliki kelebihan dan kekurangan masing-masing, namun menurut saya silakan teman-teman menggunakan tools HIDS OSSEC, tools ini m emiliki banya fitur dibandingkan dengan HIDS tripwire.

### installasi

langsung saja ke tahap installasi, OSSEC memiliki 2 tipe pengoperasian, menggunakan mode CLI dan GUI, namun disini saya akan menggunakan tools HIDS OSSEC CLI. saya menggunakan ubuntu 20.04 (focal-fossa) LTS. pada installasi kali ini saya akan memaparkan bagaimana cara menginstall ossec server dan client/agent. sebelumnya kita akan melakukan konfigurasi pada sisi server. masuk ke terminal dan lakukan update repository, sebelumnya masuk ke mode root (super user)

### server side
```bash
sudo su
```

```bash
apt-get update
```

HIDS OSSEC membutuhkan beberapa tools tambahan dalam melakukan pekerjaannya, silakan copy & paste ke terminal teman-teman.

```bash
apt-get install php gcc make libevent-dev zlib1g-dev libssl-dev libpcre2-dev wget tar -y
```

download versi terbaru dari OSSEC menggunakan wget dengan perintah.

```bash
wget https://github.com/ossec/ossec-hids/archive/3.6.0.tar.gz -P /tmp
```

setelah itu ekstrak dengan perintah.

```bash
tar xzf /tmp/3.6.0.tar.gz
```

setelah itu langkah setup, sebelumnya silakan masuk ke directory /tmp lalu ke directory ossec-hids-3.6.0

```bash 
cd /tmp/ossec-hids-3.6.0
```

lalu setup dengan perintah

```bash 
./install.sh
```
maka teman-teman akan diberikan pilihan menggunakan bahasa install, disini saya menggunakan bahasa inggris, ketikan `en`

```
** Para instalação em português, escolha [br].
  ** 要使用中文进行安装, 请选择 [cn].
  ** Fur eine deutsche Installation wohlen Sie [de].
  ** Για εγκατάσταση στα Ελληνικά, επιλέξτε [el].
  ** For installation in English, choose [en].
  ** Para instalar en Español , eliga [es].
  ** Pour une installation en français, choisissez [fr]
  ** A Magyar nyelvű telepítéshez válassza [hu].
  ** Per l'installazione in Italiano, scegli [it].
  ** 日本語でインストールします．選択して下さい．[jp].
  ** Voor installatie in het Nederlands, kies [nl].
  ** Aby instalować w języku Polskim, wybierz [pl].
  ** Для инструкций по установке на русском ,введите [ru].
  ** Za instalaciju na srpskom, izaberi [sr].
  ** Türkçe kurulum için seçin [tr].
  (en/br/cn/de/el/es/fr/hu/it/jp/nl/pl/ru/sr/tr) [en]: en
```

lalu ketikkan `enter` lagi

```

OSSEC HIDS v3.6.0 Installation Script - http://www.ossec.net
 
 You are about to start the installation process of the OSSEC HIDS.
 You must have a C compiler pre-installed in your system.
 
  - System: Linux servergobang 4.4.0-186-generic
  - User: root
  - Host: servergobang


  -- Press ENTER to continue or Ctrl-C to abort. --
```

lalu kita akan diminta untuk memilih tujuan host penginstall-an, disini silakan isi dengan `hybrid` sebagai server ossec kita, dengan mengetikan `hybrid` lalu enter.

```
1- What kind of installation do you want (server, agent, local, hybrid or help)? hybrid
```

disini kita akan diarahkan lagi, untuk memilih lokasi penyimpanan installasi OSSEC, tekan `enter` untuk path default `/var/ossec`

```
2- Setting up the installation environment.

 - Choose where to install the OSSEC HIDS [/var/ossec]: *[ENTER]*

    - Installation will be made at  /var/ossec .
```

pilih alamat IP Address host pada jaringan, sebelumnya ketikkan ifconfig untuk melakukan check ip address kita. disini saya memiliki IP Address *192.168.2.25* pada host machine saya, masukkan IP Address pada kolom input.
```
3- Configuring the OSSEC HIDS.

  3.1- What's the IP Address or hostname of the OSSEC HIDS server?: 192.168.2.25

   - Adding Server IP 192.168.2.25
```

bolehkan checking system integrity sebagai proses *daemon*

```
3.2- Do you want to run the integrity check daemon? (y/n) [y]: y

   - Running syscheck (integrity check daemon).
```

izinkan menjalankan rootkit detection engine

```
3.3- Do you want to run the rootkit detection engine? (y/n) [y]: y

   - Running rootcheck (rootkit detection).
```

Nonaktifkan respons aktif. Jika tidak, Anda dapat mengaktifkannya jika Anda memahami jenis dan jumlah peringatan yang Anda inginkan.

```
3.4 - Do you want to enable active response? (y/n) [y]: n

   - Active response disabled.
```

baiklah disini langkah setup berhasil, akan ada output path dimana ia akan menghasilkan log dari OSSEC, ketikkan `enter`.

```
3.5- Setting the configuration to analyze the following logs:
    -- /var/log/auth.log
    -- /var/log/syslog
    -- /var/log/dpkg.log
    -- /var/log/apache2/error.log (apache log)
    -- /var/log/apache2/access.log (apache log)

 - If you want to monitor any other file, just change 
   the ossec.conf and add a new localfile entry.
   Any questions about the configuration can be answered
   by visiting us online at http://www.ossec.net .
   
   
   --- Press ENTER to continue ---
```
```
*** information
jika teman-teman ingin melakukan monitor terhadap file lainnya, ubah konfigurasi yang ada pada ossec.conf dan tambahkan entri file lokal baru.
```
 

