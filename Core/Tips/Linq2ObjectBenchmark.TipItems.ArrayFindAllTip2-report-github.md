``` ini

BenchmarkDotNet=v0.11.5, OS=Windows 10.0.14393.2999 (1607/AnniversaryUpdate/Redstone1)
Intel Core i5-8500 CPU 3.00GHz (Coffee Lake), 1 CPU, 6 logical and 6 physical cores
Frequency=2929684 Hz, Resolution=341.3337 ns, Timer=TSC
.NET Core SDK=2.2.105
  [Host] : .NET Core 2.2.3 (CoreCLR 4.6.27414.05, CoreFX 4.6.27414.05), 64bit RyuJIT
  Core   : .NET Core 2.2.3 (CoreCLR 4.6.27414.05, CoreFX 4.6.27414.05), 64bit RyuJIT

Job=Core  Runtime=Core  

```
|    Method |    N |       Mean |      Error |     StdDev |     Median |  Gen 0 | Gen 1 | Gen 2 | Allocated |
|---------- |----- |-----------:|-----------:|-----------:|-----------:|-------:|------:|------:|----------:|
|    **Common** |   **10** |   **320.6 ns** |  **0.6389 ns** |  **0.5976 ns** |   **320.6 ns** | **0.0539** |     **-** |     **-** |     **256 B** |
| Optimized |   10 |   111.9 ns |  0.3111 ns |  0.2910 ns |   111.8 ns | 0.0525 |     - |     - |     248 B |
|    **Common** |  **100** | **1,098.1 ns** |  **3.7471 ns** |  **3.5050 ns** | **1,099.5 ns** | **0.2518** |     **-** |     **-** |    **1192 B** |
| Optimized |  100 |   648.9 ns |  1.2744 ns |  1.1921 ns |   648.6 ns | 0.3338 |     - |     - |    1576 B |
|    **Common** | **1000** | **6,127.2 ns** | **10.2024 ns** |  **9.0441 ns** | **6,126.0 ns** | **1.8082** |     **-** |     **-** |    **8536 B** |
| Optimized | 1000 | 4,736.5 ns | 43.6618 ns | 38.7051 ns | 4,725.6 ns | 2.6245 |     - |     - |   12416 B |
