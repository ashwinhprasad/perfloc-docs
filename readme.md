This is an implementation of a high-performance general-purpose memory allocator library written in C (Inspired by Postgres's memory contexts)

### Basic Usage

Here's a simple example of how a calling program would use Perfloc. More steps on dynamically and statically linking this program to another c program, library or executable will be added to the documentation under a separate section in the future.

```c
#include "perfloc.h"

typedef struct custom_type {
    int a;
    int arr[10];
} custom_type;

int main()
{
    MemoryChunk pmc = getPerfMem();
    custom_type* type = (custom_type*)perfalloc(pmc, sizeof(custom_type));
    type->a = 10;
    type->arr[0] = 1;
    perffree(pmc, type);
    dropPerfMem(pmc);
    return 0;
}
```

## Table Of Contents

1. [Motivation](./motivation/readme.md)  
2. [Internals](./internals/readme.md)  
3. [Contributing](./contributing/readme.md)

*For details on setting up the library and contributing, refer to the contributions section*