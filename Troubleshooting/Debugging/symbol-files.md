Symbol files, usually PDB files, contain associations between binary code and the source code. With symbol files, debuggers can interpret the binary code, thereby gaining human-readable information, such as the variable names, functions from the original source code, source code file name and even line number. Since the associations keep changing for each build, we need the PDB files that correspond to updated modules such as DLL and EXE.

Usually Symbol Files were not embedded in the module \(EXE or DLL\) thus we need to specify the symbol search path so the debugger knows where to find the symbol files.

