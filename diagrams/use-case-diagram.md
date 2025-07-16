```mermaid
graph LR
  subgraph System
    UC1>“Login”]
    UC2>“View Todos”]
    UC3>“Add Todo”]
    UC4>“Delete Todo”]
  end

  User --> UC1
  User --> UC2
  UC2 --> UC3
  UC2 --> UC4
```
