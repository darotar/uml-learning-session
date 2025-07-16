```mermaid
graph TD
  subgraph features
    subgraph auth
      LoginForm
      SignupForm
    end
    subgraph todos
      TodoList
      TodoItem
      AddTodo
    end
  end

  subgraph core
    ApiClient
    AuthContext
    TodoService
  end

  AuthContext --> ApiClient
  TodoService --> ApiClient
  LoginForm --> AuthContext
  TodoList --> TodoService
```
