``` ini

BenchmarkDotNet=v0.11.5, OS=Windows 10.0.14393.2999 (1607/AnniversaryUpdate/Redstone1)
Intel Core i5-8500 CPU 3.00GHz (Coffee Lake), 1 CPU, 6 logical and 6 physical cores
Frequency=2929684 Hz, Resolution=341.3337 ns, Timer=TSC
.NET Core SDK=2.2.105
  [Host] : .NET Core 2.2.3 (CoreCLR 4.6.27414.05, CoreFX 4.6.27414.05), 64bit RyuJIT
  Core   : .NET Core 2.2.3 (CoreCLR 4.6.27414.05, CoreFX 4.6.27414.05), 64bit RyuJIT

Job=Core  Runtime=Core  

```
|    Method |    N |       Mean |     Error |    StdDev |     Median |  Gen 0 | Gen 1 | Gen 2 | Allocated |
|---------- |----- |-----------:|----------:|----------:|-----------:|-------:|------:|------:|----------:|
|    **Common** |   **10** |   **320.3 ns** |  **1.937 ns** |  **1.812 ns** |   **320.6 ns** | **0.0539** |     **-** |     **-** |     **256 B** |
| Optimized |   10 |   129.2 ns |  2.465 ns |  2.306 ns |   128.9 ns | 0.0439 |     - |     - |     208 B |
|    **Common** |  **100** | **1,078.0 ns** | **13.177 ns** | **12.326 ns** | **1,072.2 ns** | **0.2518** |     **-** |     **-** |    **1192 B** |
| Optimized |  100 |   664.0 ns |  4.057 ns |  3.795 ns |   663.0 ns | 0.2422 |     - |     - |    1144 B |
|    **Common** | **1000** | **6,018.5 ns** | **15.951 ns** | **14.921 ns** | **6,016.1 ns** | **1.8082** |     **-** |     **-** |    **8536 B** |
| Optimized | 1000 | 4,675.0 ns | 22.839 ns | 21.364 ns | 4,667.3 ns | 1.7929 |     - |     - |    8488 B |
