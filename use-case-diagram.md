### Use Case Diagram

Aktor: Student, Freelancer, Admin

```mermaid
classDiagram
  class Student
  class Freelancer
  class Admin

  class "Login" {}
  class "Lihat Assignment" {}
  class "Kumpulkan Assignment" {}
  class "Lihat Dashboard Mahasiswa" {}

  class "Buat Project" {}
  class "Buat Board & Task" {}
  class "Kelola Tugas" {}
  class "Akses Dashboard Freelancer" {}

  class "Manajemen User" {}
  class "Lihat Semua Aktivitas" {}

  Student --> "Login"
  Student --> "Lihat Assignment"
  Student --> "Kumpulkan Assignment"
  Student --> "Lihat Dashboard Mahasiswa"

  Freelancer --> "Login"
  Freelancer --> "Buat Project"
  Freelancer --> "Buat Board & Task"
  Freelancer --> "Kelola Tugas"
  Freelancer --> "Akses Dashboard Freelancer"

  Admin --> "Login"
  Admin --> "Manajemen User"
  Admin --> "Lihat Semua Aktivitas"

  note for Student "Aktor dengan role 'student'"
  note for Freelancer "Aktor dengan role 'freelancer'"
  note for Admin "Aktor dengan role 'admin'"
```
