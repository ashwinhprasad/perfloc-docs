To use perfloc, 2 shared object libraries need to be built. These libraries are dynamically linked.

1) Collections
2) MemoryChunk

Steps to create the .so file and use them as a library in an external executable or another library is given below.


## Build Collections

```
mkdir collections/build
cd collections/build && cmake -DCMAKE_BUILD_TYPE=Debug ..
make
```


## Build Memory Chunk

```
mkdir memorychunk/build
cd memorychunk/build && cmake -DCMAKE_BUILD_TYPE=Debug ..
make
```

## Testing

```
mkdir tests/build
cd tests/build && cmake -DCMAKE_BUILD_TYPE=Debug ..
make
```
