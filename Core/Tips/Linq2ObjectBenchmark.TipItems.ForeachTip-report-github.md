``` ini

BenchmarkDotNet=v0.11.5, OS=Windows 10.0.14393.2999 (1607/AnniversaryUpdate/Redstone1)
Intel Core i5-8500 CPU 3.00GHz (Coffee Lake), 1 CPU, 6 logical and 6 physical cores
Frequency=2929684 Hz, Resolution=341.3337 ns, Timer=TSC
.NET Core SDK=2.2.105
  [Host] : .NET Core 2.2.3 (CoreCLR 4.6.27414.05, CoreFX 4.6.27414.05), 64bit RyuJIT
  Core   : .NET Core 2.2.3 (CoreCLR 4.6.27414.05, CoreFX 4.6.27414.05), 64bit RyuJIT

Job=Core  Runtime=Core  

```
|    Method |    N |        Mean |       Error |     StdDev |      Median | Gen 0 | Gen 1 | Gen 2 | Allocated |
|---------- |----- |------------:|------------:|-----------:|------------:|------:|------:|------:|----------:|
|    **Common** |   **10** |    **620.2 ns** |   **0.4253 ns** |  **0.3770 ns** |    **620.3 ns** |     **-** |     **-** |     **-** |         **-** |
| Optimized |   10 |    386.5 ns |   0.1853 ns |  0.1734 ns |    386.4 ns |     - |     - |     - |         - |
|    **Common** |  **100** |  **6,034.8 ns** |  **10.6413 ns** |  **9.9539 ns** |  **6,036.4 ns** |     **-** |     **-** |     **-** |         **-** |
| Optimized |  100 |  3,479.5 ns |   5.8151 ns |  5.1549 ns |  3,478.6 ns |     - |     - |     - |         - |
|    **Common** | **1000** | **60,552.9 ns** |  **75.9662 ns** | **71.0588 ns** | **60,563.1 ns** |     **-** |     **-** |     **-** |         **-** |
| Optimized | 1000 | 34,476.2 ns | 102.8888 ns | 96.2423 ns | 34,433.9 ns |     - |     - |     - |         - |
