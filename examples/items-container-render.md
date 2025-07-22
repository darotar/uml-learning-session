### Code Example

```tsx
import type { Item } from "./types";

import { DataPoint } from "./components/data-point";
import { shouldRenderItem } from "./util";

export const ItemsContainer: FC<{ items: Item[] }> = ({ items }) => {
  return items.filter(shouldRenderItem).map(() => <DataPoint {...item} />);
};
```

### Class Diagram

```mermaid
classDiagram

class Item
class DataPoint

class ItemsContainer {
    - items: Item[]
    + render(): DataPoint[]
}

class Util {
    <<utility>>
    + shouldRenderItem(item: Item): bool
}


ItemsContainer "1..*" -- Item : has
ItemsContainer ..> Util : uses
note for DataPoint "«constraint» creates DataPoint only if shouldRenderItem returns true"
ItemsContainer "0..*" *-- DataPoint : creates
```

### Sequence Diagram

```mermaid
sequenceDiagram
    participant C as ItemsContainer
    participant U as Util.shouldRenderItem()
    participant D as DataPoint


    C->>C: renderItems()
    loop for each item in items
        C->>U: shouldRenderItem(rec)
        alt returns true
            C->>D: new DataPoint(rec)
        end
    end
```
