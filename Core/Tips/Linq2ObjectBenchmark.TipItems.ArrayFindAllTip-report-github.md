``` ini

BenchmarkDotNet=v0.11.5, OS=Windows 10.0.14393.2999 (1607/AnniversaryUpdate/Redstone1)
Intel Core i5-8500 CPU 3.00GHz (Coffee Lake), 1 CPU, 6 logical and 6 physical cores
Frequency=2929684 Hz, Resolution=341.3337 ns, Timer=TSC
.NET Core SDK=2.2.105
  [Host] : .NET Core 2.2.3 (CoreCLR 4.6.27414.05, CoreFX 4.6.27414.05), 64bit RyuJIT
  Core   : .NET Core 2.2.3 (CoreCLR 4.6.27414.05, CoreFX 4.6.27414.05), 64bit RyuJIT

Job=Core  Runtime=Core  

```
|    Method |    N |        Mean |      Error |     StdDev |      Median |  Gen 0 | Gen 1 | Gen 2 | Allocated |
|---------- |----- |------------:|-----------:|-----------:|------------:|-------:|------:|------:|----------:|
|    **Common** |   **10** |   **115.82 ns** |  **1.9660 ns** |  **1.8390 ns** |   **115.43 ns** | **0.0100** |     **-** |     **-** |      **48 B** |
| Optimized |   10 |    39.90 ns |  0.1555 ns |  0.1455 ns |    39.85 ns | 0.0085 |     - |     - |      40 B |
|    **Common** |  **100** |   **303.93 ns** |  **1.0688 ns** |  **0.8925 ns** |   **303.65 ns** | **0.0100** |     **-** |     **-** |      **48 B** |
| Optimized |  100 |   280.12 ns |  3.1681 ns |  2.8084 ns |   279.31 ns | 0.0081 |     - |     - |      40 B |
|    **Common** | **1000** | **2,448.37 ns** | **11.6973 ns** | **10.9417 ns** | **2,445.63 ns** | **0.0267** |     **-** |     **-** |     **136 B** |
| Optimized | 1000 | 2,670.26 ns |  1.9187 ns |  1.6022 ns | 2,670.57 ns | 0.0267 |     - |     - |     128 B |
