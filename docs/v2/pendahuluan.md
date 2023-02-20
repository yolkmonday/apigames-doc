---
sidebar_position: 1
---

# Syarat & Ketentuan ! 🆕

:::warning
Ada beberapa poin yang perlu di pahami:
- **Semua HTTP Error** harus diset sebagai transaksi **Pending**
- **NETWORK TIMEOUT** harus diset sebagai transaksi **Pending**
- Flow transaksi, pada awal transaksi respon diberikan **PENDING**, untukn mendapatkan status transaksi  terbaru bisa menggunakan **API CEK STATUS** atau melalui **WEBHOOK** di halaman pengaturan webhook
- status transaksi dari apigames : **Pending, Sukses,  Gagal, Proses, Sukses Sebagian, Validasi Provider**
:::

:::info
**STATUS TRANSAKSI**

- **Pending**, transaksi awal

- **Sukses**, transaksi sukses dilakukan

- **Gagal**, transaksi gagal dilakukan

- **Proses**, transaksi sedang diproses

- **Sukses Sebagian**, dikarenakan beberapa produk di apigames merupakan gabungan dari produk nominal lainnya, contoh seperti **ML 15 DIAMOND** merupakan gabungan dari **ML 5 DIAMOND** dan **ML 10 DIAMOND**, artinya apigames harus melakukan 2x transaksi, namun yang sukses hanya sebagian.

- **Validasi Provider**, apigames tidak mendapatkan response yang seharusnya, seperti provider down atau error lainnya yang tidak dikenali oleh apigames.
:::

:::warning
Untuk mendapatkan status transaksi terbaru **JANGAN** hit ke API transaksi, tapi lakukan dengan **API CEK STATUS TRANSAKSI** atau menunggu dari **WEBHOOK / REPORT** yang apigames kirimkan.

Pada **MEMBER AREA**, sudah ditambahkan tombol resend **WEBHOOK / REPORT** manual
:::


:::warning
Status transaksi yang di percaya hanya dari **WEBHOOK / REPORT** dan **API CEK STATUS TRANSAKSI** berdasarkan status yang sudah tertera di atas.
:::

