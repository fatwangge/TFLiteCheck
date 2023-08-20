# TFLiteCheck
## Dependency
Tensorflow Lite 2.12.0  
(https://github.com/tensorflow/tensorflow)  
Flatbuffers 2.4.2?   
schema_generated.h調用VerifyField需要三個參數，flatbuffers.h這個文件的bool VerifyField()函數要增加第三個input分量，意義暫時不明）  
(https://github.com/karthickai/tflite)  
## Run
TFLiteCheck.exe ..\..\tfliteModel\classification\mobilenet_v1_1.0_224_quant.tflite  


