---
tags:
  - Coding/Linux/Commands
---

| Property Name | Function                        |
| ------------- | ------------------------------- |
| dir           | directory we want to traverse   |
| Old           | text we want to replace         |
| New           | text we want to replace it with |

```bash
find dir -name '*.md' -exec sed -i.old 's/Old/New/g' {} \;
```