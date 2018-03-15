If the version number can't tell you whether your code inside an assembly, the simpliest way to check is to decompile the assembly. There are couple of tools can do this, such as

[DotPeek](https://www.jetbrains.com/decompiler/): Installation needed. Need to use with caution when running on a dev computer, it will try find the source code from your repository instead of decompile it.

[DnSpy](https://github.com/0xd4d/dnSpy): Portable and also able to modify the assembly

[IlSpy](https://github.com/icsharpcode/ILSpy): from my experience, the code decompiled is not as good as the above two.

