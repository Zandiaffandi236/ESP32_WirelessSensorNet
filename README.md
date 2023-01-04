# ESP32_WirelessSensorNet

ESP-NOW adalah protokol yang dikembangkan oleh Espressif, yang memungkinkan banyak perangkat untuk berkomunikasi satu sama lain tanpa menggunakan Wi-Fi. Protokol ini mirip dengan konektivitas nirkabel 2.4GHz berdaya rendah. Pendifinisian alamat (MAC Address) pada masing-masing ESP32 diperlukan pada awal konfigurasi. Setelah konfigurasi alamat selesai dilakukan, jaringan peer-to-peer akan terbentuk dan perangkat tidak perlu melakukan handshaking kembali ketika akan berkomunikasi. Hal ini memunjukkan bahwa setelah perangkat ESP32 saling terpasang satu sama lain, koneksi akan tetap ada. Dengan kata lain, jika tiba-tiba salah satu ESP32 kehilangan daya atau diatur ulang, ketika restart, secara otomatis akan terhubung ke pasangan ESP32 yang telah terdefinisi alamatnya untuk melanjutkan komunikasi.<br />
ESP-NOW mempunyai fitur sebagai berikut.<br />
a) Komunikasi unicast yang terenkripsi maupun tidak terenkripsi. <br />
b) Perpaduan komunikasi data yang terenkripsi maupun yang tidak terenkripsi pada perangkat yang berada pada topologi peer-to-peer. <br />
c) Payload (ukuran) data yang dapat dikirm mencapai 250 byte.<br />
d) Terdapat fungsi callback yang dapat menginformasikan data berhasil terkirim maupun gagal dikirim.<br />
Selain itu, ESP-NOW mempunyai batasan sebagai berikut.<br />
a) Jumlah maksimal perangkat yang dapat berkomunikasi dalam mode station dengan data terenkripsi adalah 10 unit (6 dalam mode SoftAP atau SoftAP+Station). <br />
b) Untuk komunikasi tidak terenkripsi, jumlah maksimal perangkat adalah 20 unit, termasuk dengan yang terenkripsi. <br />
ESP-NOW mempunyai 2 tipe jaringan, yaitu One-Way Communication dan Two-Way Communication. One-Way Communication terbagi menjadi Point-to-Point, One-to-Many Communication dan Many-to-One Communication. Sementara Two-Way Communication terbagi menjadi Point-to-Point dan Mesh Communication.

**ALAT DAN BAHAN**
1) ESP32
2) Breadboard
3) Kabel jumper
4) Resistor 10K Ohm

**HASIL KELUARAN**

**1) Memperoleh MAC Address ESP32 Receiver**

![image](https://user-images.githubusercontent.com/41616849/210596531-fc717dc1-c1f3-46c6-9bb3-f112f9e9aa40.png)


**2) ESP-NOW One-Way Point-to-Point Communication** <br />
`MAC Address Tx : 24:0A:C4:C6:06:54`

![image](https://user-images.githubusercontent.com/41616849/210597498-a57b845e-6eb0-4aa8-8eac-e40055b32e34.png)

![image](https://user-images.githubusercontent.com/41616849/210598239-43ba5003-0efb-49f4-a38a-8e11caeaa36b.png)


`MAC Address Rx : 30:AE:A4:7A:8F:B8`

![image](https://user-images.githubusercontent.com/41616849/210597777-b3ec9c2e-91f1-492c-939a-c9de0610f04a.png)


![image](https://user-images.githubusercontent.com/41616849/210597866-62455995-f8c9-4c77-a3ff-97fbd65a82fd.png)


![image](https://user-images.githubusercontent.com/41616849/210597931-a7975ec0-1c6c-4038-8582-21a78b5f0755.png)


**3) ESP-NOW One-Way, One-to-Many Communication** <br />
Mengirim Pesan yang Sama Ke Beberapa Board ESP32 MAC Address yang digunakan: <br />
`MAC Sender : 3C:71:BF:F1:4B:08`  <br />
`MAC Reciver 1 : 24:6F:28:02:C3:1C` <br />
`MAC Receiver 2 : 24:0A:C4:C6:06:54` <br />
`MAC Receiver 3 : 30:AE:A4:7A:8F:B8` <br />
Pada Receiver 3, Hasilnya adalah sebagai berikut.
![image](https://user-images.githubusercontent.com/41616849/210599119-a8c816a9-1b0a-4002-9446-2966bc308d63.png)

Pada Receiver 3 saat dimatikan board receiver, Hasilnya adalah sebagai berikut.
![image](https://user-images.githubusercontent.com/41616849/210599262-df7aed34-4dc8-4e88-b314-68936c900c9e.png)


**4) ESP-NOW One-Way, Many-to-One Communication ** <br />
MAC Address ESP32 yang digunakan :

`MAC Sender 1 : 24:0A:C4:C5:E2:DC`

`MAC Sender 2 : 24:0A:C4:C6:06:54`

`MAC Sender 3 : 24:0A:C4:C6:0E:7C`

`MAC Receiver  : 3C:71:BF:F1:42:70`

Dari Pihak Sender akan muncul seperti dibawah.
![image](https://user-images.githubusercontent.com/41616849/210600154-e8054f55-0cb7-478c-a130-749a2ccde257.png)


Dari Pihak Receiver akan muncul seperti dibawah.
![image](https://user-images.githubusercontent.com/41616849/210600276-3534bd9b-b8d0-4892-aa46-e36b2bded987.png)


**5) ESP-NOW Two-Way Communication** <br />
Rangkaian :
![image](https://user-images.githubusercontent.com/41616849/210600912-9ca87d69-d5c9-45ec-b586-e668b79b8f98.png)
![image](https://user-images.githubusercontent.com/41616849/210601147-6d0c7912-7adb-4468-9615-ac87a3530611.png)

Tampilan Serial Monitor :
![image](https://user-images.githubusercontent.com/41616849/210601254-46f34b79-907b-4e46-a410-7cf00ddf1129.png)













