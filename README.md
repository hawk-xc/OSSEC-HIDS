# OSSEC-HIDS
OSSEC (Open Source HIDS SECurity) merupakan salah satu tools profesional kemanan cyber, dimana tools ini digunakan sebagai HIDS. HIDS sendiri memiliki kepanjangan (Host Intrusion Detection System), dimana tools ini melakukan monitoring dan melaporkan kejadian/intrusi pada suatu perangkat host. selain HIDS OSSEC ada juga tools HIDS tripwire, keduanya memiliki kelebihan dan kekurangan masing-masing, namun menurut saya silakan teman-teman menggunakan tools HIDS OSSEC, tools ini m emiliki banya fitur dibandingkan dengan HIDS tripwire.

### installasi

langsung saja ke tahap installasi, OSSEC memiliki 2 tipe pengoperasian, menggunakan mode CLI dan GUI, namun disini saya akan menggunakan tools HIDS OSSEC CLI. saya menggunakan ubuntu 20.04 (focal-fossa) LTS. masuk ke terminal dan lakukan update repository, sebelumnya masuk ke mode root (super user)

```bash
sudo su
```

```bash
apt-get update
```

HIDS OSSEC membutuhkan beberapa tools tambahan dalam melakukan pekerjaannya, silakan copy & paste ke terminal teman-teman.

```bash
apt-get install gcc make libevent-dev zlib1g-dev libssl-dev libpcre2-dev wget tar -y
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

`
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
`



