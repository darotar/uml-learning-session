Dropdown Component State

```mermaid
stateDiagram
 [*] --> Closed

 Closed --> Opened: click toggle
 Opened --> Focused: focus item
 Opened --> Closed: click outside
 Focused --> Opened: blur item

 Closed: render button only
 Opened: render list
 Focused: highlight item
```
