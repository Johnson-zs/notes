# cmake

## demo

### hello world

1. 初始化
    ```bash
    touch CMakeLists.txt main.c
    ```
2. main.c
    ```c
    #include <stdio.h>
 
    int main()
    {
        printf("Hello World from ex_01 Main!\n");
        return 0;
    }
   ```
3. CMakeLists.txt
    ```cmake
    # CMakeLists.txt
    CMAKE_MINIMUM_REQUIRED(VERSION 2.8)
    
    PROJECT(HELLO)
    
    SET(SRC_LIST main.c)
    
    MESSAGE(STATUS "This is BINARY dir " ${HELLO_BINARY_DIR})
    MESSAGE(STATUS "This is SOURCE dir " ${HELLO_SOURCE_DIR})
    
    # <==> ADD_EXECUTABLE(hello main.c)
    ADD_EXECUTABLE(hello ${SRC_LIST})
    ```
4. build
    ```bash
    mkdir build
    cd build
    cmake ..
    make
    ./hello
    ```
### hello world 工程



## 概念


## 参考资料

- [CMake_快速入门](https://durant35.github.io/2016/04/21/tool_CMake_%E5%BF%AB%E9%80%9F%E5%85%A5%E9%97%A8/)
- [Cmake 实践](https://durant35.github.io/uploads/CMake%20Practice.pdf)