### Activity Diagram - Alur Umum Pengguna

```mermaid
stateDiagram-v2
  [*] --> Login
  Login --> Authenticated
  Authenticated --> Check Role

  state Check Role {
    [*] --> Student
    [*] --> Freelancer
    [*] --> Admin
  }

  state Student {
    ViewDashboard --> ViewAssignment
    ViewAssignment --> SubmitAssignment
    SubmitAssignment --> [*]
  }

  state Freelancer {
    ViewDashboardFreelancer --> CreateProject
    CreateProject --> CreateKanbanBoard
    CreateKanbanBoard --> AddTasks
    AddTasks --> [*]
  }

  state Admin {
    ViewAdminPanel --> ManageUsers
    ManageUsers --> ViewActivityLogs
    ViewActivityLogs --> [*]
  }
```
