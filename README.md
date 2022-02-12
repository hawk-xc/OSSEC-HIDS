# OSSEC-HIDS
OSSEC (Open Source HIDS SECurity) merupakan salah satu tools profesional kemanan cyber, dimana tools ini digunakan sebagai HIDS. HIDS sendiri memiliki kepanjangan (Host Intrusion Detection System), dimana tools ini melakukan monitoring dan melaporkan kejadian/intrusi pada suatu perangkat host. selain HIDS OSSEC ada juga tools HIDS tripwire, keduanya memiliki kelebihan dan kekurangan masing-masing, namun menurut saya silakan teman-teman menggunakan tools HIDS OSSEC, tools ini memiliki banya fitur dibandingkan dengan tripwire.

### installasi

langsung saja ke tahap installasi, OSSEC memiliki 2 tipe pengoperasian, menggunakan mode CLI dan GUI, namun disini saya akan menggunakan tools HIDS OSSEC CLI. saya menggunakan ubuntu 20.04 (focal-fossa) LTS. masuk ke terminal dan lakukan update repository, sebelumnya masuk ke mode root (super user)

```bash
sudo su
```

```bash
apt-get install update
```


