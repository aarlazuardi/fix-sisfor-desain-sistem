### Sequence Diagram Lengkap untuk Semua Role

#### Mahasiswa Membuat Assignment

```mermaid
sequenceDiagram
  participant Student
  participant Frontend
  participant Backend
  participant Database

  Student->>Frontend: Login
  Frontend->>Backend: Kirim kredensial
  Backend->>Database: Validasi user
  Database-->>Backend: User valid
  Backend-->>Frontend: Token login
  Frontend-->>Student: Tampilkan dashboard

  Student->>Frontend: Klik "Buat Assignment"
  Frontend->>Student: Tampilkan form
  Student->>Frontend: Submit form
  Frontend->>Backend: Kirim data Assignment
  Backend->>Database: Simpan data Assignment
  Database-->>Backend: Konfirmasi
  Backend-->>Frontend: Assignment berhasil
  Frontend-->>Student: Redirect ke halaman Assignment
```

#### Mahasiswa Mengelola Kanban

```mermaid
sequenceDiagram
  participant Student
  participant Frontend
  participant Backend
  participant Database

  Student->>Frontend: Buat board baru
  Frontend->>Backend: Kirim data board
  Backend->>Database: Simpan board
  Database-->>Backend: OK
  Backend-->>Frontend: Tampilkan board

  Student->>Frontend: Tambah task
  Frontend->>Backend: Simpan task
  Backend->>Database: Simpan task ke board
  Database-->>Backend: OK
  Backend-->>Frontend: Tampilkan task

  Student->>Frontend: Assign user ke task
  Frontend->>Backend: Simpan assignment
  Backend->>Database: Simpan ke TaskAssignee
  Database-->>Backend: OK
```

#### Freelancer Melihat dan Mengambil Project

```mermaid
sequenceDiagram
  participant Freelancer
  participant Frontend
  participant Backend
  participant Database

  Freelancer->>Frontend: Login
  Frontend->>Backend: Kirim kredensial
  Backend->>Database: Validasi user
  Database-->>Backend: User valid
  Backend-->>Frontend: Token login
  Frontend-->>Freelancer: Dashboard freelancer

  Freelancer->>Frontend: Klik "Lihat Project"
  Frontend->>Backend: Fetch data Project
  Backend->>Database: Ambil semua project
  Database-->>Backend: Data project
  Backend-->>Frontend: Tampilkan project
  Frontend-->>Freelancer: List project tampil
```

#### Freelancer Komentar dan Upload
<<<<<<< HEAD

=======
>>>>>>> bd9ebe384a77c79410868d5342db204afca197fb
```mermaid
sequenceDiagram
  participant Freelancer
  participant Frontend
  participant Backend
  participant Database

  Freelancer->>Frontend: Buka task
  Frontend->>Backend: Ambil detail task
  Backend->>Database: Fetch task + komentar
  Database-->>Backend: Data lengkap
  Backend-->>Frontend: Tampilkan detail

  Freelancer->>Frontend: Kirim komentar
  Frontend->>Backend: Simpan komentar
  Backend->>Database: Insert ke Comment
  Database-->>Backend: OK

  Freelancer->>Frontend: Upload file
  Frontend->>Backend: Kirim file
  Backend->>Database: Simpan ke Attachment
  Database-->>Backend: OK
```
