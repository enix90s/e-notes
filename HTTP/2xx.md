Kode status HTTP **2xx** menunjukkan bahwa permintaan dari klien berhasil diproses oleh server. Berikut adalah daftar kode status **2xx**, penjelasannya, dan contoh penggunaannya:

---

### **200 OK**
Digunakan ketika permintaan berhasil diproses dan respons mengandung data yang diminta.

#### Contoh
**Permintaan**:
```http
GET /api/products HTTP/1.1
Host: example.com
```

**Respons**:
```http
HTTP/1.1 200 OK
Content-Type: application/json

{
    "products": [
        {"id": 1, "name": "Laptop", "price": 1500},
        {"id": 2, "name": "Smartphone", "price": 800}
    ]
}
```

---

### **201 Created**
Digunakan ketika permintaan berhasil menghasilkan sumber daya baru di server.

#### Contoh
**Permintaan**:
```http
POST /api/products HTTP/1.1
Host: example.com
Content-Type: application/json

{
    "name": "Tablet",
    "price": 500
}
```

**Respons**:
```http
HTTP/1.1 201 Created
Content-Type: application/json
Location: /api/products/3

{
    "id": 3,
    "name": "Tablet",
    "price": 500
}
```

---

### **202 Accepted**
Digunakan ketika permintaan telah diterima untuk diproses, tetapi pemrosesan belum selesai.

#### Contoh
**Permintaan**:
```http
POST /api/reports HTTP/1.1
Host: example.com
Content-Type: application/json

{
    "reportType": "sales",
    "dateRange": "2023-01-01 to 2023-12-31"
}
```

**Respons**:
```http
HTTP/1.1 202 Accepted
Content-Type: application/json

{
    "message": "Your report is being generated. You will be notified when it's ready."
}
```

---

### **204 No Content**
Digunakan ketika permintaan berhasil diproses, tetapi tidak ada data yang dikembalikan dalam respons.

#### Contoh
**Permintaan**:
```http
DELETE /api/products/3 HTTP/1.1
Host: example.com
```

**Respons**:
```http
HTTP/1.1 204 No Content
```

---

### **206 Partial Content**
Digunakan ketika server hanya mengirimkan sebagian data dari sumber daya, biasanya dalam konteks pengunduhan file atau streaming.

#### Contoh
**Permintaan**:
```http
GET /files/video.mp4 HTTP/1.1
Host: example.com
Range: bytes=0-1023
```

**Respons**:
```http
HTTP/1.1 206 Partial Content
Content-Type: video/mp4
Content-Range: bytes 0-1023/2048

[Binary video data...]
```

---

### **208 Already Reported**
Digunakan dalam konteks **WebDAV**, ketika elemen yang sama telah dilaporkan sebelumnya dalam respons.

#### Contoh
**Permintaan**:
```http
PROPFIND /api/files HTTP/1.1
Host: example.com
```

**Respons**:
```http
HTTP/1.1 208 Already Reported
Content-Type: application/xml

<response>
    <href>/api/files/document1.txt</href>
    <status>HTTP/1.1 200 OK</status>
</response>
```

---

### **226 IM Used**
Digunakan jika server berhasil memproses permintaan menggunakan **delta encoding** untuk mengurangi jumlah data yang dikirimkan.

#### Contoh
**Permintaan**:
```http
GET /api/resource HTTP/1.1
Host: example.com
A-IM: feed
```

**Respons**:
```http
HTTP/1.1 226 IM Used
Content-Type: application/json

{
    "resource": "Updated using delta encoding"
}
```

---

Kode **2xx** menandakan keberhasilan pemrosesan permintaan dan memberikan informasi penting bagi klien tentang hasil atau status dari permintaan tersebut.