# API Gateway Heksa Insurance x Chip Sakti
PT Asuransi Heksa Insurance X Chip Sakti 
___________________________________________________________

### Request List Product
#### URL & Params Required:
##### - Features
  - Sender : **Chip Sakti**
  - Target API : **Heksa Insurance**
  - Request List Product from Heksa Insurance
#

##### - PRODUK
  - Asuransi Micro Perisai Diri Extra
#

##### - Endpoint
  - **PRODUCTION**
```sh
https://store.heksainsurance.co.id/partner/api/chipsakti/reqproduct
```
  - **DEVELOPMENT**
```sh
http://103.58.146.64/heksa-partner/api/chipsakti/reqproduct
```
#

##### - Method : GET
#

##### - Authorization Basic Auth

| Params | Data Type | Mandatory | Length | Description |
|--|--|--|--|--|
|username| [text] | Y |150 |Username untuk basic auth - diberi oleh heksa insurance |
|password|[text] | Y |150 |Password basic auth - diberi oleh heksa insurance |

##### - Result Structure
| Params | | Data Type | Mandatory | Length | Description |
|--|--|--|--|--|--|
| ProductCode |  | [Text] | Y | 10 | Kode Produk |
| ProductName |  | [Text] | Y | 100 | Nama Produk |
| ProductDescription |  | [Text] | Y | 1500 | Deskripsi Produk |
| ProductTermofService |  | [Text] | Y | 1500 | Term of Service Produk |
| ProductNote |  | [Text] | Y | 1500 | Statement ini di taruh di bukti pembayaran yang nasabah terima |
| ProductBannerUrl |  | [Text] | Y | 500 | URL Banner Image |
#

###### Success Response
```sh
{
  "ProductCode": "HI-X11",
  “ProductName": "Asuransi Micro Perisai Diri Extra 5000",
  “ProductDescription": "Produk asuransi mikro yang memberikan manfaat perlindungan atas risiko meninggal dunia karena kecelakaan pada masa pertanggungan, dengan perluasan pilihan manfaat Meninggal dunia karena alami/sakit (bukan karena kecelakaan) dan/atau Cacat tetap dan total karena kecelakaan dan/atau Penggantian biaya pengobatan/perawatan di rumah sakit karena kecelakaan dan/atau Cacat tetap dan total akibat penyakit",
  “ProductTermofService": "Saya setuju pertanggungan asuransi dimulai sejak premi dibayarkan dan aktivasi pengajuan asuransi berhasil dilakukan.",
  “ProductNote": ""Segera aktivasi asuransi Anda melalui link berikut ini :https://heksainsurance.co.id/perisaidiri/extra/aktivasi*) Apabila dalam waktu 2 hari tidak melakukan aktivasi maka pembelian ini dibatalkan otomatis dan premi akan dikembalikan ke rekening Anda"",
  “ProductBannerUrl": "https://heksainsurance.co.id/assets/image/produk/heksa-mikroPerisaiDiriExtra.png"
}
```
#
###### Failed Response
```sh
{
    "StatusCode": "400",
    "StatusMessage": "Internal Error",
    "Value" : [
      array string error
    ]
}
```
#
____________________________________________________________________


### Request Kode Aktivasi
#### URL & Params Required:
##### - Features
  - Sender : **Chip Sakti**
  - Target API : **Heksa Insurance**
  - Request Activation Code from Heksa Insurance
#

##### - PRODUK
  - Asuransi Micro Perisai Diri Extra
#


##### - Endpoint
  - **PRODUCTION**
```sh
https://store.heksainsurance.co.id/partner/api/chipsakti/reqactivationcode
```
  - **DEVELOPMENT**
```sh
http://103.58.146.64/heksa-partner/api/chipsakti/reqactivationcode
```
#

##### - Method : POST
#

##### - Authorization Basic Auth

| Params | Data Type | Mandatory | Length | Description |
|--|--|--|--|--|
|username| [text] | Y |150 |Username untuk basic auth - diberi oleh heksa insurance |
|password|[text] | Y |150 |Password basic auth - diberi oleh heksa insurance |

#
##### - Body Structure
| Params | | Data Type | Mandatory | Length | Description |
|--|--|--|--|--|--|
| TransactionID |  | [Text] | Y | 30 | ID Transaksi digenerate oleh Chipsakti |
| ProductCode |  | [Text] | Y | 10 | List Product dari Product yang heksa kirim |
| PhoneNo |  | [Text] | Y | 20 | Nomor Telepon Nasabah Sesuai yang diinputkan Nasabah |
| TransactionDate |  | [Text] | Y | dd/MM/yyyy HH:mm:ss | Tanggal dan Jam Trnsaksi Nasabah |
| AgentID |  | [Text] | Y | 1500 | ID Agent atau ID User yang login ke Aplikasi Chipsakti |
| AgentName |  | [Text] | Y | 500 | Nama Agent atau Nama User yang login ke aplikasi Chipsakti |
#

###### Json Request
```sh
{
  "TransactionID": "xxxxxxxx",
  "ProductCode": "HI-X11",
  "PhoneNo": "82353162965",
  "TransactionDate": "19/06/2021 6:16:35",
  "AgentID": "988456746",
  "AgentName": "SAMSURIADI S"
}
```
#

##### - Result Structure
| Params | | Data Type | Mandatory | Length | Description |
|--|--|--|--|--|--|
| TransactionID |  | [Text] | Y | 30 | ID Transaksi yang digenerate oleh Chipsakti |
| ActivationCode |  | [Array Text] | Y | 100 | Kode aktivasi 5 digit huruf dan angka dikirim dalam Array String  |
| ActivationUrl |  | [Text] | Y | 1500 | Url untuk nasabah melakukan aktivasi |
| ActivationTimeOut |  | [Text] | Y | datetime | string format date time (dd-MM-yyyy HH:mm:ss) format jam 24Jam |
#

###### Success Response
```sh
{
  "TransactionID": "xxxxxxxx",
  “ActivationCode": [“b97ca”,”dm87ba”],
  “ActivationUrl:” https://heksainsurance.co.id/perisaidiri/extra/aktivasi”,
  “ActiovationTimeOut:”02-07-2021 14:50:20”
}
```
#
###### Failed Response
```sh
{
    "StatusCode": "500",
    "StatusMessage": "There is an error in system",
    "Value" : 
}
```
#
____________________________________________________________________

### Return Validate Activation
#### URL & Params Required:
##### - Features
  - Sender : **Heksa Insurance**
  - Target API : **Chipsakti**
  - Send Activation Result from **Heksa Insurance** to **Chipsakti** API 
#

##### - PRODUK
  - Asuransi Micro Perisai Diri Extra
#

##### - Endpoint
  - **PRODUCTION**
```sh
Ditentukan oleh chipsakti
```
  - **DEVELOPMENT**
```sh
Ditentukan oleh chipsakti
```
#

##### - Method : POST
#

##### - Authorization Basic Auth

| Params | Data Type | Mandatory | Length | Description |
|--|--|--|--|--|
|username| [text] | Y |150 |Username untuk basic auth - diberi oleh Chipsakti |
|password|[text] | Y |150 |Password basic auth - diberi oleh Chipsakti |


##### - Result Structure
| Params | | Data Type | Mandatory | Length | Description |
|--|--|--|--|--|--|
| TransactionID |  | [Text] | Y | 30 | ID Transaksi yang digenerate oleh Chipsakti |
| ActivationCode |  | [Array Text] | Y | 100 | Kode aktivasi 5 digit huruf dan angka dikirim dalam Array String  |
| StatusCode |  | [Text] | Y | 3 | Kode Status Menandakan Status Transaksi yang terjadi |
| note |  | [Text] | Y | 1500 | Note dari Status Transaksi |
#

###### Success Response
```sh
{
  "TransactionID": "xxxxxxxx",
  “ActivationCode": “b97ca",
  “StatusCode": “400", 
  “Note": “Transaksi Gagal, Usia Tidak Valid",
}
```

____________________________________________________________________

#### List Status Code
Status Code yang heksa kirim ke Chipsakti
___________________________________________________________
- 200 -> Transaksi Berhasil dan Polis Berhasil Terbentuk!
- 400 -> Transaksi Gagal (Lihat Note Terkait Gagalnya transaksi)
____________________________________________________________________

#### Pernyataan Nasabah
Saya setuju pertanggungan asuransi dimulai sejak premi dibayarkan dan aktivasi pengajuan asuransi berhasil dilakukan.

#### Note di Bukti Bayar
Segera aktivasi asuransi Anda melalui link berikut ini :https://heksainsurance.co.id/perisaidiri/extra/aktivasi
*) Apabila dalam waktu 2 hari tidak melakukan aktivasi maka pembelian ini dibatalkan otomatis dan premi akan dikembalikan ke rekening Anda

#### FLOW SYSTEM
![image](https://user-images.githubusercontent.com/42398592/124553507-06aa1000-de5f-11eb-9a0c-7303d8d05234.png)
