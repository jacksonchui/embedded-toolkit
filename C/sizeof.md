# sizeof

`size_t (*sizeof)(storage_space_symbol)`. A storage space symbol can be an expression, variable or type cast (i.e. type). It is mainly used for dynamic memory allocation.

## Get the `sizeof` a static array

Use `sizeof` to find the memory used by or the count of a static array.

``` c
int arr[] = { 1, 2, 3, 4, 5};
const size_t arrMemoryUsed = sizeof(arr);
const size_t arrElemCount = arrMemoryUsed / sizeof(*arr); // or sizeof(arr[0]);
```

## `sizeof` for for dynamic memory allocation

Use `sizeof` to dynamically allocate memory depending on compiler. For example `int` can either be 4 or 8 bytes depending on if you use a 32-bit or 64-bit c compiler.

``` C
const int count = 10;
int *arr = (int *)malloc(count * sizeof(int));
// sizeof(arr) is either 4 or 8 bytes
```