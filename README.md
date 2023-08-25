# TFLiteCheck
## Build
mkdir build  
cd build  
cmake ..  
Open TFLiteCheck.sln in Visual Studio and build  
## How to run
Make sure to build in release, x64
Go to build\Release\
Enter this command:
TFLiteCheck.exe ..\\..\tfliteModel\classification\mobilenet_v1_1.0_224_quant.tflite  
## Dependency
Tensorflow Lite 2.12.0  
(https://github.com/tensorflow/tensorflow)  
Flatbuffers 2.4.2?   
schema_generated.h: calls VerifyField(), 3 arguments. 
flatbuffers.h: need add the 3rd arg to bool VerifyField()  
(https://github.com/karthickai/tflite)  
## Build Info of tensorflowlite.dll
Python 3.11.4
msys2-x86_64-20230718
VS2019
Tensorflow 2.12.0
ROCm support: N
arch: AVX
Eigen: Y
Bazel 5.3.0
Build Command:
bazel build -c opt //tensorflow/lite:tensorflowlite
##
This project is created with Visual Studio 2019
Can not use MinGW because the library is generated by MS compiler
