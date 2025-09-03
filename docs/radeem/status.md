---
sidebar_position: 5
---

# Cek Status Radeem

Melakukan radeem voucher secara bulk (lebih dari 1 voucher) menggunakan method POST

## Endpoint

```bash
https://v1.apigames.id/merchant/[merchant_id]/kiosgamer/project/detail
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
| session_key | Session Key Kiosgamer anda | String    | Ya    |
| signature   | Signature dengan formula **md5(merchant_id + secret_key)**      | String    | Ya    |

### Contoh

```json
{
    "projectid":"DW",
    "status":"", //kosong jika tidak melakukan pencarian by status
    "page":1,
    "limit":30,
    "signature":"fa375f4e30dbe2cdcf5d1ee0e9d678ef"
}
```

## Response

### Deskripsi

### Contoh Response Sukses

```json
{
    "status": 1,
    "rc": 200,
    "message": "List Voucher Redem Kiosgamer",
    "data": {
        "current_page": 1,
        "data": {
            "id": 5847,
            "merchant_id": "M240315GAME2847K",
            "project_id": "R240815XPQR000012",
            "total_voucher": 3,
            "vouchers": [
                {
                    "id": 23456,
                    "project_id": "R240815XPQR000012",
                    "voucher_code": "ABC123DEF456GHI",
                    "response_json": "",
                    "note": "-",
                    "nominal_gs": 0,
                    "created": "2024-08-15",
                    "cretaed_at": "2024-08-15 14:32:18",
                    "updated_at": "2024-08-15 14:32:18",
                    "status": 0
                },
                {
                    "id": 23455,
                    "project_id": "R240815XPQR000012",
                    "voucher_code": "JKL789MNO012PQR",
                    "response_json": "",
                    "note": "-",
                    "nominal_gs": 0,
                    "created": "2024-08-15",
                    "cretaed_at": "2024-08-15 14:32:18",
                    "updated_at": "2024-08-15 14:32:18",
                    "status": 0
                },
                {
                    "id": 23454,
                    "project_id": "R240815XPQR000012",
                    "voucher_code": "STU345VWX678YZ9",
                    "response_json": "",
                    "note": "-",
                    "nominal_gs": 25,
                    "created": "2024-08-15",
                    "cretaed_at": "2024-08-15 14:32:18",
                    "updated_at": "2024-08-15 14:32:18",
                    "status": 0
                }
            ],
            "kategori_voucher": [
                {
                    "name": "0",
                    "total": 2
                },
                {
                    "name": "25",
                    "total": 1
                }
            ],
            "stats": {
                "pending": 3,
                "success": 0,
                "process": 0,
                "error_engine": 0,
                "error_voucher": 0
            }
        },
        "total_data": 3,
        "total_page": 1
    },
    "ts": 1723719138
}
```

### Contoh Response Gagal

#### 1. Invalid JSON Data
```json
{
  "status": 0,
  "rc": 400,
  "error_msg": "Data JSON tidak valid"
}
```

#### 2. Merchant Not Found
```json
{
  "status": 0,
  "rc": 500,
  "error_msg": "Merchant not found"
}
```

#### 3. Invalid Signature
```json
{
  "status": 0,
  "rc": 500,
  "error_msg": "Signature Not Valid"
}
```

#### 4. Project Not Found
```json
{
  "status": 0,
  "rc": 500,
  "error_msg": "Project ID tidak ditemukan"
}
```
