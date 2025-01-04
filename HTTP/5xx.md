Kode status HTTP **5xx** menunjukkan bahwa terjadi kesalahan pada sisi server. Berikut adalah daftar kode status **5xx** yang umum digunakan, penjelasannya, dan contoh lengkapnya:

---

### **500 Internal Server Error**
Digunakan ketika server mengalami kesalahan umum yang tidak diharapkan.

#### Contoh
**Permintaan**:
```http
GET /api/orders HTTP/1.1
Host: example.com
```

**Respons**:
```http
HTTP/1.1 500 Internal Server Error
Content-Type: application/json

{
    "error": "An unexpected error occurred. Please try again later."
}
```

---

### **501 Not Implemented**
Digunakan jika metode HTTP atau fitur yang diminta belum diimplementasikan pada server.

#### Contoh
**Permintaan**:
```http
PATCH /api/products/1 HTTP/1.1
Host: example.com
```

**Respons**:
```http
HTTP/1.1 501 Not Implemented
Content-Type: application/json

{
    "error": "PATCH method is not supported for this resource."
}
```

---

### **502 Bad Gateway**
Digunakan jika server bertindak sebagai gateway atau proxy dan menerima respons yang tidak valid dari server upstream.

#### Contoh
**Permintaan**:
```http
GET /api/external-service HTTP/1.1
Host: example.com
```

**Respons**:
```http
HTTP/1.1 502 Bad Gateway
Content-Type: application/json

{
    "error": "Failed to receive a valid response from the upstream server."
}
```

---

### **503 Service Unavailable**
Digunakan jika server tidak dapat menangani permintaan karena kelebihan beban atau sedang dalam pemeliharaan.

#### Contoh
**Permintaan**:
```http
GET /api/products HTTP/1.1
Host: example.com
```

**Respons**:
```http
HTTP/1.1 503 Service Unavailable
Content-Type: application/json
Retry-After: 120

{
    "error": "The service is temporarily unavailable. Please try again later."
}
```

---

### **504 Gateway Timeout**
Digunakan jika server bertindak sebagai gateway atau proxy dan tidak menerima respons tepat waktu dari server upstream.

#### Contoh
**Permintaan**:
```http
GET /api/external-data HTTP/1.1
Host: example.com
```

**Respons**:
```http
HTTP/1.1 504 Gateway Timeout
Content-Type: application/json

{
    "error": "The upstream server did not respond in time."
}
```

---

### **505 HTTP Version Not Supported**
Digunakan jika server tidak mendukung versi HTTP yang digunakan oleh klien.

#### Contoh
**Permintaan**:
```http
GET /api/products HTTP/2.0
Host: example.com
```

**Respons**:
```http
HTTP/1.1 505 HTTP Version Not Supported
Content-Type: application/json

{
    "error": "HTTP version 2.0 is not supported."
}
```

---

### **508 Loop Detected**
Digunakan jika server menemukan loop tak terhingga saat memproses permintaan (biasanya dalam konteks WebDAV atau sistem distributed).

#### Contoh
**Permintaan**:
```http
PROPFIND /api/files HTTP/1.1
Host: example.com
```

**Respons**:
```http
HTTP/1.1 508 Loop Detected
Content-Type: application/json

{
    "error": "A loop was detected in the request processing."
}
```

---

### **511 Network Authentication Required**
Digunakan jika klien perlu melakukan autentikasi jaringan, biasanya dalam konteks captive portal (misalnya, Wi-Fi publik).

#### Contoh
**Permintaan**:
```http
GET /api/resource HTTP/1.1
Host: example.com
```

**Respons**:
```http
HTTP/1.1 511 Network Authentication Required
Content-Type: application/json

{
    "error": "Network authentication is required to access this resource."
}
```

---

Kode status **5xx** menunjukkan bahwa masalah ada di sisi server, sehingga perlu ditangani oleh pengembang backend atau administrator server untuk memperbaiki kesalahan tersebut.