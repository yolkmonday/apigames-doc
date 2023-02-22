---
sidebar_position: 4
---

# Deposit


:::warning
Merupakan API untuk deposit **SALDO APIGAMES**.
Untuk saat ini hanya support via Transfer Bank.
:::
## Endpoint

```bash
https://v1.apigames.id/v2/deposit-get?merchant=[YOUR_MERCHANT_CODE]&nominal=[NOMINAL]&secret=[YOUR_SECRET]
```

## HTTP Method

```
GET
```

## Request

### Deskripsi

Berikut adalah parameter yang di harapkan

| Parameter   | Deskripsi                                                                                        | Tipe Data | Wajib |
| ----------- | ------------------------------------------------------------------------------------------------ | --------- | ----- |
| merchant | Merchant ID Anda [Lihat Pengaturan Secret Key](https://member.apigames.id/pengaturan/secret-key) | String    | Ya    |
| nominal | Nominal Deposit Anda           | String    | Ya    |
| secret | Secret Key Anda [Lihat Pengaturan Secret Key](https://member.apigames.id/pengaturan/secret-key) | String    | Ya    |

### Contoh

```bash
https://v1.apigames.id/v2/deposit-get?merchant=[YOUR_MERCHANT_CODE]&nominal=100000&secret=[YOUR_SECRET]
```

## Response Deposit

```json
{
    "status": 1,
    "rc": 200,
    "message": "tiket deposit",
    "data": {
        "admin": 2000,
        "expired": "2023-02-22 23:59:00",
        "id": 46,
        "kode_unik": 3,
        "nominal": 10000,
        "rekening": "BCA 8455510119 An Dewa",
        "total_transfer": 12003
    },
    "ts": 1677058571
}
```


