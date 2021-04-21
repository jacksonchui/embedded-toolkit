# Allocating Memory

## `memset`

> Library: `<string.h>`
>
> `void *memset(void *str, int c, size_t n)`

`memset` copies unsigned char `c` to the first `n` characters pointed to by `str`. You can use it also to zero an

### Example

``` C
#include <stdio.h>
#include <string.h>

int main () {
    char str[12];

    // setup example
    strcpy(str, "Hello World");
    puts(str);

    // &(str[0]) == str
    memset(&(str[0]), '$', 5);
    puts(str);

    return 0;
}
// "Hello World"
// "$$$$$ World"
```

### Zero an an array

`memset` is commonly used to zero arrays in C. It is written in pure assembly.

``` C
memset(myarray, 0, sizeof(myarray)); // for static arrays
memset(myarray, 0, N*sizeof(*myarray)); // for heap dynamically-allocated arrays
```