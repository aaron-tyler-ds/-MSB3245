# -MSB3245
This repo contains an example project tree that triggers a MSB3245 warning that is promoted to an error where dotnet.exe build still returns a 0 exit code.

Build the \src\exe folder to reproduce the issue. Example output:

 C:\repos\MSB3277\src\exe>dotnet build
 Microsoft (R) Build Engine version 16.7.0+7fb82e5b2 for .NET
 Copyright (C) Microsoft Corporation. All rights reserved.

  Determining projects to restore...
  Restored C:\repos\MSB3277\src\classlib1\classlib1.csproj (in 124 ms).
  Restored C:\repos\MSB3277\src\classlib2\classlib2.csproj (in 124 ms).
  Restored C:\repos\MSB3277\src\classlib3\classlib3.csproj (in 124 ms).
  Restored C:\repos\MSB3277\src\exe\exe.csproj (in 124 ms).
  classlib1 -> C:\repos\MSB3277\src\classlib1\bin\Debug\net47\classlib1.dll
  classlib2 -> C:\repos\MSB3277\src\classlib2\bin\Debug\net47\classlib2.dll
  classlib3 -> C:\repos\MSB3277\src\classlib3\bin\Debug\net47\classlib3.dll
C:\Program Files\dotnet\sdk\3.1.403\Microsoft.Common.CurrentVersion.targets(2084,5): error MSB3245: Could not resolve this reference. Could not locate the assembly "FooBar.Baz". Check to make sure the assembly exists on disk. If this reference is required by your code, you may get compilation errors. [C:\repos\MSB3277\src\exe\exe.csproj]
  exe -> C:\repos\MSB3277\src\exe\bin\Debug\net47\exe.exe

 Build succeeded.

 C:\Program Files\dotnet\sdk\3.1.403\Microsoft.Common.CurrentVersion.targets(2084,5): error MSB3245: Could not resolve this reference. Could not locate the assembly "FooBar.Baz". Check to make sure the assembly exists on disk. If this reference is required by your code, you may get compilation errors. [C:\repos\MSB3277\src\exe\exe.csproj]
    0 Warning(s)
    1 Error(s)

 Time Elapsed 00:00:01.06

 C:\repos\MSB3277\src\exe>echo %errorlevel%
 0