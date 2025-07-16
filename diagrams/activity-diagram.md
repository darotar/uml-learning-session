Login Form Activity Diagram

```mermaid
flowchart TD
  Start([Start]) --> Input[“Enter credentials”]
  Input --> Validate{Valid?}
  Validate -- Yes --> CallService[“call AuthService”]
  CallService --> Success{Success?}
  Success -- Yes --> Redirect[“redirect to dashboard”]
  Success -- No  --> ShowErr[“show error message”] --> End([End])
  Validate -- No  --> ShowErr --> End
```
