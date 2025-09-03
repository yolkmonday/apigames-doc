---
sidebar_position: 5
---

# Radeem Voucher Garena Shell Kiosgamer

Melakukan radeem voucher secara bulk (lebih dari 1 voucher) menggunakan method POST

## Endpoint

```bash
https://v1.apigames.id/merchant/[merchant_id]/kiosgamer/redem/bulk
```

## HTTP Method

```
POST
```

## Request

### Deskripsi

Berikut adalah struktur JSON yang diharapkan:

| Parameter   | Deskripsi                                                                                        | Tipe Data | Wajib |
| ----------- | ------------------------------------------------------------------------------------------------ | --------- | ----- |
| kode_voucher      | Base64 dari list voucher anda, bisa menggunakan bantuan [Base64Encode] (https://www.base64encode.org/) atau library dari bahasa yang anda gunakan. **Jangan lupa pisahkan dengan enter di setiap kode voucher       **                                                                           | String    | Ya    |
| session_key | Session Key Kiosgamer anda,  jika di kosongkan akan mengambil data session key dari koneksi akun | String    | Tidak    |
| signature   | Signature dengan formula **md5(merchant_id + secret_key)**      | String    | Ya    |

### Contoh

```json

{
    "kode_voucher":"d2VmZXdmd2Vmd2VmZXdmCndlZmV3ZndlZndlZndlZndlZgp3ZWZ3ZWZ3ZWZld2Zld2Y=",
    "signature":"fa375f4e30dbe2cdcf5d1ee0e9d678ef",
    "session_key":"nfeiwin34nin43infi3f"

}
```

## Response

### Deskripsi

### Contoh Response Sukses

```json
{
  "status": 1,
  "rc": 0,
  "message": "Sukses Memasukan Voucher Ke Antrian",
   "data": {
        "id": 23,
        "merchant_id": "M220122XXXX374A",
        "project_id": "R220414JXXX0021",
        "project_name": "R220414JXXXXXX021",
        "total_voucher": 0,
        "total_cost": 0,
        "total_bayar": 0,
        "saldo_before_trx": 0,
        "saldo_after_trx": 0,
        "unipin_session": "",
        "unipin_xsrf_token": "4rwer",
        "unipin_token_redeem": "",
        "unipin_email": "admin@xxxx.net",
        "balance_uc_start": 0,
        "balance_uc_end": 0,
        "balance_up_start": 0,
        "balance_up_end": 0,
        "s_pending": 0,
        "s_success": 0,
        "s_process": 0,
        "s_error_engine": 0,
        "s_error_voucher": 0,
        "created": "",
        "created_at": "",
        "status": 0,
        "updated_at": ""
    },
  "ts": 1705312200
}
```

### Contoh Response Gagal

#### 1. Missing Required Fields
```json
{
  "status": 0,
  "rc": 500,
  "error_msg": "JSON tidak valid"
}
```

#### 2. Invalid Signature
```json
{
  "status": 0,
  "rc": 500,
  "error_msg": "Signature Not Valid"
}
```

#### 3. Maintenance Mode
```json
{
  "status": 0,
  "rc": 500,
  "error_msg": "Redem sedang maintenance"
}
```

#### 4. Invalid Base64 Voucher
```json
{
  "status": 0,
  "rc": 500,
  "error_msg": "Data voucher bulk harus dalam bentuk bas64encode"
}
```

#### 5. Merchant Not Found
```json
{
  "status": 0,
  "rc": 500,
  "error_msg": "Merchant not found"
}
```

#### 6. Merchant Config Error
```json
{
  "status": 0,
  "rc": 500,
  "error_msg": "Merchant config not found"
}
```

#### 7. Account Info Error
```json
{
  "status": 0,
  "rc": 500,
  "error_msg": "Error getting account info from KiosGamer"
}
```

#### 8. Project Creation Error
```json
{
  "status": 0,
  "rc": 500,
  "error_msg": "Error creating project redemption"
}
```

#### 9. Voucher Insertion Error
```json
{
  "status": 0,
  "rc": 500,
  "error_msg": "Error inserting voucher data"
}
```

#### 10. Duplicate Voucher Error
```json
{
  "status": 0,
  "rc": 500,
  "error_msg": "Voucher ini double, sudah ada sebelumnya"
}
```
