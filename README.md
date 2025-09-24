### Things to note for Apriltag port:
Memory Limitations
- In the source files for each apriltag family, there is an array called `codedata` where each entry corresponds to a tag id (I believe).
- This eventually gets converted to a lookup table, which can take up a lot of memory for the full tag family
- Currently I have commented most of the tags out (Look at the code for the corresponding modifications)
Compiler issues
- The current RISCV compiler for ESP32 (xtensa?) treats `int32_t` as `long int` instead of `int`. `int` is the corresponding macro in gcc which is likely what the apriltag library is intended for.
- Refer to the `CMakeList.txt` for the `esp_apriltag` component to see the fix
- This involves redefining a macro which may be a source of a lot of bugs 
- I only replaced the macro for the signed 32bit integer, I got a lot of errors when trying to do the same for unsigned, but the behaviour is acceptable without this modification
- I believe the ESP32 compiler defined a 16 bit signed integer for int, so this is a possible source of bugs to note in the future

### Other Issues and things to note for implementation
- Pixel format must be set to grayscale
- Detection capability is very depedent on the detection parameters (so needs further tuning)
- Can experiment with the resolution, I used QVGA but can go higher at the expense of performance.
- In esp-idf config, enable PSRAM, set to Octal
