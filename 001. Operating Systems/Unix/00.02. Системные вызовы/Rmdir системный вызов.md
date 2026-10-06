#flashcards/os/Unix  
***
[[Системный вызов]] для удаления пустого каталога.
***Синтаксис.***
```C
#include <unistd.h>

int rmdir(const char *pathname);
```
- `pathname` - строка с указанием пути к каталогу.
- Возвращает по классике `0` или `-1`.