---
title: Matlab Coder(M语言转译成C或C++语言)
date: 2017-12-11 16:44:05
tags:
- Matlab
- C
categories: 开发
---
> 当你使用M语言开发的算法，想移植到使用Linux做为操作系统的arm智能设备上时，Matlab Coder是一个非常棒的工具。使用Matlab Coder生成的C/C++代码不需要依赖于matlab，也不需要依赖于MCR。

## 1. 打开Matlab，安装默认的编译器，在Command Window窗口中输入mex -setup。

```
>> mex -setup

Welcome to mex -setup.  This utility will help you set up
a default compiler.  For a list of supported compilers, see
http://www.mathworks.com/support/compilers/R2013b/win64.html

Please choose your compiler for building MEX-files:

Would you like mex to locate installed compilers [y]/n? y

Select a compiler:
[1] Microsoft Visual C++ 2012 in D:\Program Files\Microsoft Visual Studio 11.0
[2] Microsoft Visual C++ 2010 in C:\Program Files (x86)\Microsoft Visual Studio 10.0

[0] None

Compiler: 2

Please verify your choices:

Compiler: Microsoft Visual C++ 2010
Location: C:\Program Files (x86)\Microsoft Visual Studio 10.0

Are these correct [y]/n? y

***************************************************************************
Warning: MEX-files generated using Microsoft Visual C++ 2010 require
that Microsoft Visual Studio 2010 run-time libraries be
available on the computer they are run on.
If you plan to redistribute your MEX-files to other MATLAB
users, be sure that they have the run-time libraries.
***************************************************************************


Trying to update options file: C:\Users\Administrator\AppData\Roaming\MathWorks\MATLAB\R2013b\mexopts.bat
From template:              C:\PROGRA~1\MATLAB\R2013b\bin\win64\mexopts\msvc100opts.bat

Done . . .

**************************************************************************
Warning: The MATLAB C and Fortran API has changed to support MATLAB
variables with more than 2^32-1 elements.  In the near future
you will be required to update your code to utilize the new
API. You can find more information about this at:
http://www.mathworks.com/help/matlab/matlab_external/upgrading-mex-files-to-use-64-bit-api.html
Building with the -largeArrayDims option enables the new API.
**************************************************************************
```

## 2. 选择APPS->MATLAB Coder，创建项目。

![](Matlab-Coder-M语言转译成C或C-语言\MATLABCoder.png)
![](Matlab-Coder-M语言转译成C或C-语言\MATLABCoderNewProject.png)

## 3. 设置项目生成的类型：C/C++ Static Library。

![](Matlab-Coder-M语言转译成C或C-语言\MATLABCoderSettingOutputTypeCorCplusplusStaticLibrary.png)

## 4. 添加M函数，可以是多个，这里只使用的一个m函数：test.m

```m
function r = test(x, y)
    r = round(x+y);
end
```

![](Matlab-Coder-M语言转译成C或C-语言\MATLABCoderEntryPointAddFiles.png)
![](Matlab-Coder-M语言转译成C或C-语言\MATLABCoderEntryPointDefineParamterType.png)

## 5. 生成C/C++代码。

![](Matlab-Coder-M语言转译成C或C-语言\MATLABCoderGenerateCorCplusplusCode.png)
![](Matlab-Coder-M语言转译成C或C-语言\BuildFinished.png)
![](Matlab-Coder-M语言转译成C或C-语言\CodeGenerationReport.png)

## 参考

1. [Matlab Coder的使用](http://blog.csdn.net/lzh2912/article/details/52622328)
