---
title: Demo
description: Demo Bootcamp Marp Template
_class:
  - lead
footer: Presentation Title | Author Name
_footer: ""
paginate: true
_paginate: false
marp: true
theme: d8niz
---

---

# Outline

- Marp Header
- Bullet Points
- Tables
- Images
- Code
- References

---

# Marp Header

<style scoped>
pre {
   font-size: 2rem;
   background-color: #000;
}
</style>

```yml
title: Demo
description: Demo TUM Marp Template
_class: # First slide
  - lead # Title slide style
footer: Presentation Title | Author Name # Slide footer
_footer: "" # No footer on title slide
paginate: true # Page numbers
_paginate: false # No page numbers on title slide
marp: true # Nice preview for the VS Code extension
```

---

# Bullet Points

- Show all
- at once

* or one
* by one

---

# Tables

| Header | Header | Header |
| ------ | ------ | ------ |
| Text   | Text   | Text   |
| Text   | Text   | Text   |
| Text   | Text   | Text   |

---

# Images

![](assets/academy.jpg)

---

## Background Images

- Full Size

![bg right](./assets/academy.jpg)

---

## Background Images Customized

- 60% slide width
- 80% image size

![bg right:60% 80%](./assets/academy.jpg)

---

# Code

<style scoped>
pre {
   font-size: 2rem;
   background-color: #000
}
</style>

```cpp
#include <iostream>

int main(int /*argc*/, char** /*argv*/)
{
    std::cout << "Code with syntax highlighting!" << std::endl;

    return EXIT_SUCCESS;
}

```

---

## References

- [Get Started](https://github.com/marp-team/marp)
- [Documentation](https://marpit.marp.app/)
- [CLI](https://github.com/marp-team/marp-cli)
