### Activity Diagram - Alur Umum Pengguna

```mermaid
---
config:
  layout: elk
  look: neo
  theme: default
---
%% Activity Diagram: Alur Student dan Freelancer
stateDiagram-v2

state "Student - Buat Assignment" as StudentAssignment {
  [*] --> Login
  Login --> Dashboard
  Dashboard --> CreateAssignment : Click "New Assignment"
  CreateAssignment --> FillForm : Input Title, Description, Deadline
  FillForm --> SubmitForm : Click "Submit"
  SubmitForm --> AssignmentCreated : Save to Database
  AssignmentCreated --> ViewAssignment : Redirect to Assignment Page
  ViewAssignment --> [*]
}

state "Student - Kelola Kanban" as StudentKanban {
  [*] --> Dashboard
  Dashboard --> CreateBoard : Click "New Kanban Board"
  CreateBoard --> AddTask : Tambahkan Task
  AddTask --> AssignTask : Tambah Penugasan
  AssignTask --> Save : Simpan Task
  Save --> [*]
}

state "Freelancer - Akses Proyek" as FreelancerProject {
  [*] --> Login
  Login --> Dashboard
  Dashboard --> ViewProjects : Klik "Lihat Project"
  ViewProjects --> ReadProjectDetail : Lihat Detail Project
  ReadProjectDetail --> AcceptTask : Ambil Task
  AcceptTask --> [*]
}

state "Freelancer - Komentar dan Upload" as FreelancerTask {
  [*] --> TaskPage
  TaskPage --> Comment : Tambah Komentar
  Comment --> Upload : Upload Attachment
  Upload --> [*]
}
```
