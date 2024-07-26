To use Perfloc, 2 shared object libraries need to be built. These libraries are dynamically linked.

1) Collections
2) MemoryChunk

Steps to create the .so file and use it as a library in an external executable or another library are given below.


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

## My Vscode Launch.json contents for debugging

```js
{
    "version": "0.2.0",
    "configurations": [
        {
            "name": "(gdb) Launch",
            "type": "cppdbg",
            "request": "launch",
            "program": "${workspaceFolder}/tests/build/test",
            "args": [],
            "stopAtEntry": false,
            "cwd": "${fileDirname}",
            "environment": [],
            "externalConsole": false,
            "MIMode": "gdb",
            "setupCommands": [
                {
                    "description": "Enable pretty-printing for gdb",
                    "text": "-enable-pretty-printing",
                    "ignoreFailures": true
                },
                {
                    "description": "Set Disassembly Flavor to Intel",
                    "text": "-gdb-set disassembly-flavor intel",
                    "ignoreFailures": true
                }
            ]
        }

    ]
}

```

[Back to Home](./readme.md)