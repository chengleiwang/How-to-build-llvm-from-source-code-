# How-to-build-llvm-from-source-code
1. Download minmal necessary source code from http://releases.llvm.org/download.html, and then copy them into clang-8.0.0 floder<br>
    LLVM source code<br>
    Clang source code<br>
    compiler-rt source code<br>
    libc++ source code<br>
    libc++abi source code<br>
    clang-tools-extra<br>

2. unzip all above zip file with tar xf xxx.xz command.<br>
   `tar xf llvm-8.0.0.src.tar.xz`<br>
   ...<br>

3. mv ./llvm-8.0.0/llvm-8.0.0.src llvm<br>
   cd llvm/tools<br>
   mv ../../llvm-8.0.0/cfe-8.0.0.src clang<br>
   cd ../..<br>
  
   cd llvm/tools/clang/tools<br>
   mv ../../../../llvm-8.0.0/clang-tools-extra-8.0.0.src extra<br>
   cd ../../../..<br>

   cd llvm/projects<br>
   mv ../../llvm-8.0.0/compiler-rt-8.0.0.src compiler-rt<br>
   mv ../../llvm-8.0.0/libcxx-8.0.0.src libcxx<br>
   mv ../../llvm-8.0.0/libcxxabi-8.0.0.src libcxxabi<br>
   cd ../..

4. mkdir build<br>
   cd build<br>
   sudo cmake -DCMAKE_BUILD_TYPE=Release ../llvm <br>
   sudo cmake --build . -- -j10<br>
   sudo cmake --build . --target install<br>

5. check clang version with clang -v<br>
