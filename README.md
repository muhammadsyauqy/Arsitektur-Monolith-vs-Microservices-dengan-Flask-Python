### Bagian 1: Menjalankan Aplikasi Monolith

#### 1. Jalankan Aplikasi:
   Buka terminal dan jalankan file monolith:
   ```bash
   python monolith_app.py
   ```
   *(Biarkan terminal ini tetap aktif)*

#### 2. Uji Coba Endpoint:
   Buka terminal baru untuk mengetes API menggunakan `curl`:
   
   * Melihat daftar buku:
     ```bash
     curl http://localhost:5000/books
     ```
   * Membuat pesanan baru:
     ```bash
     curl -X POST -H "Content-Type: application/json" -d "{\"book_id\": 1}" http://localhost:5000/orders
     ```

### Bagian 2: Menjalankan Aplikasi Microservices

#### 1. Jalankan Book Service (Terminal 1):
   ```bash
   python book_service.py
   ```

#### 2. Jalankan Order Service (Terminal 2):
   ```bash
   python order_service.py
   ```

#### 3. Uji Coba Aplikasi (Terminal 3):
   Kirim permintaan pembuatan pesanan ke **Order Service** (port 5002):
   ```bash
   curl -X POST -H "Content-Type: application/json" -d "{\"book_id\": 1}" http://localhost:5002/orders
   ```
