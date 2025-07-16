```mermaid
graph TD
  subgraph AppShell
    Header
    Content
    Footer
  end

  subgraph TodoFeature
    TodoList
    TodoItem
    AddTodo
  end

  subgraph AuthFeature
    LoginForm
    SignupForm
  end

  AppShell --> AuthFeature
  AppShell --> TodoFeature
  TodoFeature --> AuthFeature
```
