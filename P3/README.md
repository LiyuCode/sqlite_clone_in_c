
Here I found the code blocks like the following would raise `initializer element is not constant` compiling error.

```
const uint32_t ID_OFFSET = 0;
const uint32_t USERNAME_OFFSET = ID_OFFSET + ID_SIZE; /*Here, `initializer element is not constant`*/
```

This is because the author was working on Mac with `Clang` as compiler.

So, to simplify, we switch to `clang` as the compiler.
To do this, `SET(CMAKE_C_COMPILER /usr/bin/clang)` is added in `CMakeLists.txt`.

You may want to ensure `clang` has installed on your Ubuntu before continue.
This can be done with `sudo apt install llvm clang -y`.

Now we are good to continue `Part 3` the 'db.c'.

