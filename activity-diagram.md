### Activity Diagram - Alur Umum Pengguna

```mermaid
---
config:
  layout: elk
  look: classic
  theme: default
---
flowchart TB
  %% INIT
  Start([Start])
  Login[/User Login/]
  RoleCheck{Has Selected Role?}
  SelectRole[/Select Role/]
  Route[[Route to Dashboard]]
  RoleSplit{Role == Student?}

  %% STUDENT BLOCK
  subgraph Student Flow
    SC1[/View Courses/]
    SC2[/Create Course/]
    SA1[/View Assignments/]
    SA2[/Create Assignment/]
    SK1[/Open Assignment Kanban/]
    SK2[/Update Task Status/]
    ST1[/Access Settings/]
    SLogout[/Logout/]
  end

  %% FREELANCER BLOCK
  subgraph Freelancer Flow
    FP1[/View Projects/]
    FP2[/Create Project/]
    FT1[/View Tasks/]
    FT2[/Create Task/]
    FA1[/Assign Task/]
    FK1[/Open Kanban Board/]
    FTmpl[/Use Templates/]
    FSet[/Access Settings/]
    FLogout[/Logout/]
  end

  %% Flow
  Start --> Login --> RoleCheck
  RoleCheck -- No --> SelectRole --> Route
  RoleCheck -- Yes --> Route
  Route --> RoleSplit

  %% Student Path
  RoleSplit -- Yes --> SC1 --> SC2 --> SA1 --> SA2 --> SK1 --> SK2 --> ST1 --> SLogout

  %% Freelancer Path
  RoleSplit -- No --> FP1 --> FP2 --> FT1 --> FT2 --> FA1 --> FK1 --> FTmpl --> FSet --> FLogout

  SLogout --> End([End])
  FLogout --> End
```
