## Project Description

.NET bindings for OpenCL that are easy-to-use and true to the original API. There is no OOP abstraction, nor will there ever be. OpenCL.Net is meant to be small, fast (with as little explicit marshaling as possible) and .NET friendly at the same time.

OpenCL.NET now generates type-safe kernel wrappers using a custom build step. Steps to use it are:
1. Fetch the latest [OpenCL.NET](https://www.nuget.org/packages/OpenCL.Net/) package from Nuget
2. Add a kernel (say _kernel.cl_) and write code in it as usual
3. Go to Properties for that file and choose **"Kernel"** as the Build Action
4. You can either choose the "Copy the file to the output directory" option (in which case the wrapper will reference this file to load sources) or leave it at **"Do not copy"** which will cause OpenCL.Net to embed the kernel source code in the wrapper.
5. Simply instantiate and use the kernel as shown [here](https://github.com/mikhail-khalizev/OpenCL.Net/blob/master/Samples/Simple/Program.cs)

For the curious-minded, the actual kernel wrapper is generated as _obj/<yourKernelName>.Kernel.cs_ and included in the compile process, much like App.xaml.g.cs. 

_**Note:** OpenCL.NET does not support custom types or complex preprocessor-based parameter type definitions at this time. Contact me if something you would very much like to have does not work._

OpenCL.NET is now available on Nuget! Get it [here](http://www.nuget.org/List/Packages/OpenCL.Net)
