``` ini

BenchmarkDotNet=v0.11.5, OS=Windows 10.0.14393.2999 (1607/AnniversaryUpdate/Redstone1)
Intel Core i5-8500 CPU 3.00GHz (Coffee Lake), 1 CPU, 6 logical and 6 physical cores
Frequency=2929684 Hz, Resolution=341.3337 ns, Timer=TSC
.NET Core SDK=2.2.105
  [Host] : .NET Core 2.2.3 (CoreCLR 4.6.27414.05, CoreFX 4.6.27414.05), 64bit RyuJIT
  Core   : .NET Core 2.2.3 (CoreCLR 4.6.27414.05, CoreFX 4.6.27414.05), 64bit RyuJIT

Job=Core  Runtime=Core  

```
|    Method |    N |        Mean |     Error |    StdDev |      Median |  Gen 0 | Gen 1 | Gen 2 | Allocated |
|---------- |----- |------------:|----------:|----------:|------------:|-------:|------:|------:|----------:|
|    **Common** |   **10** |   **182.91 ns** | **0.2799 ns** | **0.2618 ns** |   **182.82 ns** | **0.0236** |     **-** |     **-** |     **112 B** |
| Optimized |   10 |    34.24 ns | 0.0628 ns | 0.0557 ns |    34.24 ns | 0.0085 |     - |     - |      40 B |
|    **Common** |  **100** |   **889.69 ns** | **1.4375 ns** | **1.3446 ns** |   **889.70 ns** | **0.0229** |     **-** |     **-** |     **112 B** |
| Optimized |  100 |   225.77 ns | 0.3804 ns | 0.3559 ns |   225.64 ns | 0.0083 |     - |     - |      40 B |
|    **Common** | **1000** | **7,940.10 ns** | **8.7399 ns** | **8.1753 ns** | **7,937.98 ns** | **0.0153** |     **-** |     **-** |     **112 B** |
| Optimized | 1000 | 2,120.80 ns | 6.5099 ns | 6.0894 ns | 2,120.51 ns | 0.0076 |     - |     - |      40 B |
