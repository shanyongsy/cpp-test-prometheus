# cpp-test-prometheus

## build prometheus-cpp-dev lib
### code
- from https://github.com/jupp0r/prometheus-cpp/tree/v1.1.0
### build sdk lib
#### fetch third-party dependencies
```
git submodule init
git submodule update
mkdir _build
cd _build
```
#### run cmake
- for 32bit
```
cmake .. -DBUILD_SHARED_LIBS=OFF -DENABLE_PUSH=OFF -DENABLE_COMPRESSION=OFF -DCMAKE_INSTALL_PREFIX="../install" -DCMAKE_C_FLAGS=-m32 -DCMAKE_CXX_FLAGS=-m32
```
```
- for 64bit
 cmake .. -DBUILD_SHARED_LIBS=OFF -DENABLE_PUSH=OFF -DENABLE_COMPRESSION=OFF -DCMAKE_INSTALL_PREFIX="../install" -DCMAKE_C_FLAGS=-m64 -DCMAKE_CXX_FLAGS=-m64
```
#### build
```
cmake --build . --parallel 4
```
#### run tests
```
ctest -V
```
#### install the libraries and headers
```
cmake --install .
```
## build test code
### build
```
mkdir _build
cd _build
cmake ..
make
```
### run
```
./main -p 9090
```
