Berikut adalah contoh kode status **4xx** yang umum digunakan, penjelasannya, dan contoh lengkapnya:

---

### **400 Bad Request**
Digunakan ketika permintaan klien tidak valid, seperti format yang salah atau data yang tidak sesuai.

#### Contoh
**Permintaan**:
```http
POST /api/register HTTP/1.1
Host: example.com
Content-Type: application/json

{
    "username": "user123",
    "password": 12345
}
```

**Respons**:
```http
HTTP/1.1 400 Bad Request
Content-Type: application/json

{
    "error": "Invalid password format. Password must be a string."
}
```

---

### **401 Unauthorized**
Digunakan jika klien tidak memberikan otentikasi atau token otentikasi tidak valid.

#### Contoh
**Permintaan**:
```http
GET /api/profile HTTP/1.1
Host: example.com
Authorization: Bearer invalid_token
```

**Respons**:
```http
HTTP/1.1 401 Unauthorized
Content-Type: application/json
WWW-Authenticate: Bearer

{
    "error": "Invalid or missing authentication token."
}
```

---

### **403 Forbidden**
Digunakan jika klien tidak memiliki izin untuk mengakses sumber daya meskipun sudah terotentikasi.

#### Contoh
**Permintaan**:
```http
DELETE /api/admin/users/1 HTTP/1.1
Host: example.com
Authorization: Bearer valid_token
```

**Respons**:
```http
HTTP/1.1 403 Forbidden
Content-Type: application/json

{
    "error": "You do not have permission to perform this action."
}
```

---

### **404 Not Found**
Digunakan jika sumber daya yang diminta tidak ditemukan.

#### Contoh
**Permintaan**:
```http
GET /api/products/999 HTTP/1.1
Host: example.com
```

**Respons**:
```http
HTTP/1.1 404 Not Found
Content-Type: application/json

{
    "error": "Product with ID 999 not found."
}
```

---

### **405 Method Not Allowed**
Digunakan jika metode HTTP tidak diizinkan untuk sumber daya.

#### Contoh
**Permintaan**:
```http
PUT /api/products HTTP/1.1
Host: example.com
```

**Respons**:
```http
HTTP/1.1 405 Method Not Allowed
Content-Type: application/json
Allow: GET, POST

{
    "error": "PUT method is not allowed for this resource."
}
```

---

### **422 Unprocessable Entity**
Digunakan jika data yang dikirim valid secara sintaks, tetapi tidak valid secara semantik.

#### Contoh
**Permintaan**:
```http
POST /api/register HTTP/1.1
Host: example.com
Content-Type: application/json

{
    "username": "user123",
    "password": "short"
}
```

**Respons**:
```http
HTTP/1.1 422 Unprocessable Entity
Content-Type: application/json

{
    "error": "Password must be at least 8 characters long."
}
```

---

### **429 Too Many Requests**
Digunakan jika klien mengirim terlalu banyak permintaan dalam waktu singkat.

#### Contoh
**Permintaan**:
```http
GET /api/resource HTTP/1.1
Host: example.com
```

**Respons**:
```http
HTTP/1.1 429 Too Many Requests
Content-Type: application/json
Retry-After: 60

{
    "error": "Too many requests. Please try again after 60 seconds."
}
```

---

Kode status ini digunakan untuk menangani berbagai situasi error pada permintaan klien, sehingga aplikasi dapat memberikan informasi yang jelas dan membantu klien memperbaiki masalah.

