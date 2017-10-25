---
title: Swift Call C
date: 2017-10-25 17:21:47
tags:
- Xcode
- Swift
- C
categories: 开发
---

## C 类型对应 Swift 类型

C Type |                   Swift Type
-|-
bool |                      CBool
char, signed char |         CChar
unsigned char |             CUnsignedChar
short |                     CShort
unsigned short |            CUnsignedShort
int  |                      CInt
unsigned int |              CUnsignedInt
long |                      CLong
unsigned long |             CUnsignedLong
long long |                 CLongLong
unsigned long long |        CUnsignedLongLong
wchar_t |                   CWideChar
char16_t  |                 CChar16
char32_t  |                 CChar32
float |                     CFloat
double |                    CDouble
char* |                     UnsafeMutablePointer<Int8>

## 配置 Objective-C Bridging Header 文件

- 打开 Objective-C Bridging Header 文件：SwiftCallC-Bridging-Header.h，添加调用 C 定义的头文件。

``` swift
#import "XXX.h"
```

## 编写 C 代码

``` c

void NoParamterAndNoReturn(void) {
    printf("Call NoParamterAndNoReturn Function\n");
}

void SetParamters(char c, unsigned char uc,
                  short int16, unsigned short uint16,
                  int int32, unsigned int uint32,
                  long long32, unsigned long ulong32,
                  long long long64, unsigned long long ulong64,
                  float float32, double float64,
                  const char* inStr) {
    printf("Call SetParamters Function\n");
    printf("char %d, unsigned char %u\n", c, uc);
    printf("short %d, unsigned short %u\n", int16, uint16);
    printf("int %d, unsigned int %u\n", int32, uint32);
    printf("long %ld, unsigned long %lu\n", long32, ulong32);
    printf("long long %lld, unsigned long long %llu\n", long64, ulong64);
    printf("float %f, double %f\n", float32, float64);
    printf("in char* %s\n", inStr);
}

void GetPointerParamters(char* c, unsigned char* uc,
                         short* int16, unsigned short* uint16,
                         int* int32, unsigned int* uint32,
                         long* long32, unsigned long* ulong32,
                         long long* long64, unsigned long long* ulong64,
                         float* float32, double* float64,
                         char* outStr) {
    printf("Call GetPointerParamters Function\n");
    *c = 'A';
    *uc = 255;
    *int16 = -16;
    *uint16 = 16;
    *int32 = -32;
    *uint32 = 32;
    *long32 = -32;
    *ulong32 = 32;
    *long64 = -64;
    *ulong64 = 64;
    *float32 = 32.32;
    *float64 = 64.64;
    strcpy(outStr, "Goodbye!");
}

int Add(int x, int y) {
    return x + y;
}
```

## Swift Call C

``` swift
override func viewDidLoad() {
    super.viewDidLoad()
    
    NoParamterAndNoReturn()
    
    callSetParamters()
    
    callGetPointerParamters()
  
    print(Add(10, 20))
}

private func callSetParamters() {
    let c: CChar = 127
    let uc: CUnsignedChar = 255
    let int16: CShort = -16
    let uint16: CUnsignedShort = 16
    let int32: CInt = -32
    let uint32: CUnsignedInt = 32
    let long32: CLong = -32
    let ulong32: CUnsignedLong = 32
    let long64: CLongLong = -64
    let ulong64: CUnsignedLongLong = 64
    let float32: CFloat = 32.32
    let float64: CDouble = 64.64
    let inStr = "Hello!"

    SetParamters(c, uc, int16, uint16, int32, uint32,
                 long32, ulong32, long64, ulong64,
                 float32, float64, inStr)
}

private func callGetPointerParamters() {
    var c: CChar = 0
    var uc: CUnsignedChar = 0
    var int16: CShort = 0
    var uint16: CUnsignedShort = 0
    var int32: CInt = 0
    var uint32: CUnsignedInt = 0
    var long32: CLong = 0
    var ulong32: CUnsignedLong = 0
    var long64: CLongLong = 0
    var ulong64: CUnsignedLongLong = 0
    var float32: CFloat = 0.0
    var float64: CDouble = 0.0

    let cPtr = UnsafeMutablePointer(&c)
    let ucPtr = UnsafeMutablePointer(&uc)
    let int16Ptr = UnsafeMutablePointer(&int16)
    let uint16Ptr = UnsafeMutablePointer(&uint16)
    let int32Ptr = UnsafeMutablePointer(&int32)
    let uint32Ptr = UnsafeMutablePointer(&uint32)
    let long32Ptr = UnsafeMutablePointer(&long32)
    let ulong32Ptr = UnsafeMutablePointer(&ulong32)
    let long64Ptr = UnsafeMutablePointer(&long64)
    let ulong64Ptr = UnsafeMutablePointer(&ulong64)
    let float32Ptr = UnsafeMutablePointer(&float32)
    let float64Ptr = UnsafeMutablePointer(&float64)
    
    let bufSize = 100
    let outStrPtr = UnsafeMutablePointer<Int8>.allocate(capacity: bufSize)  //分配内存
    
    GetPointerParamters(cPtr, ucPtr, int16Ptr, uint16Ptr, int32Ptr, uint32Ptr,
                        long32Ptr, ulong32Ptr, long64Ptr, ulong64Ptr,
                        float32Ptr, float64Ptr, outStrPtr)
    
    let outStr = String.init(cString: outStrPtr)
    outStrPtr.deallocate(capacity: bufSize)    //释放内存
    
    print("char \(c), unsigned char \(uc)\n",
        "short \(int16), unsigned short \(uint16)\n",
        "int \(int32), unsigned int \(uint32)\n",
        "long \(long32), unsigned long \(ulong32)\n",
        "long long \(long64), unsigned long long \(ulong64)\n",
        "float \(float32), double \(float64)\n",
        "out char* \(outStr)\n")
}
```

## 参考

1. [Interacting with C APIs](https://developer.apple.com/library/content/documentation/Swift/Conceptual/BuildingCocoaApps/InteractingWithCAPIs.html)
2. [Swift Call C sample](https://github.com/vwarship/Samples/tree/master/iOS/Practice/SwiftCallC)

