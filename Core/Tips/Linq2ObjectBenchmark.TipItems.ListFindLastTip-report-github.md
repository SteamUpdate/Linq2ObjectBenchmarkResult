``` ini

BenchmarkDotNet=v0.11.5, OS=Windows 10.0.14393.2999 (1607/AnniversaryUpdate/Redstone1)
Intel Core i5-8500 CPU 3.00GHz (Coffee Lake), 1 CPU, 6 logical and 6 physical cores
Frequency=2929684 Hz, Resolution=341.3337 ns, Timer=TSC
.NET Core SDK=2.2.105
  [Host] : .NET Core 2.2.3 (CoreCLR 4.6.27414.05, CoreFX 4.6.27414.05), 64bit RyuJIT
  Core   : .NET Core 2.2.3 (CoreCLR 4.6.27414.05, CoreFX 4.6.27414.05), 64bit RyuJIT

Job=Core  Runtime=Core  

```
|    Method |    N |        Mean |     Error |    StdDev |      Median | Gen 0 | Gen 1 | Gen 2 | Allocated |
|---------- |----- |------------:|----------:|----------:|------------:|------:|------:|------:|----------:|
|    **Common** |   **10** |    **63.70 ns** | **0.0441 ns** | **0.0391 ns** |    **63.69 ns** |     **-** |     **-** |     **-** |         **-** |
| Optimized |   10 |    20.82 ns | 0.0107 ns | 0.0095 ns |    20.82 ns |     - |     - |     - |         - |
|    **Common** |  **100** |   **455.44 ns** | **0.5807 ns** | **0.5432 ns** |   **455.58 ns** |     **-** |     **-** |     **-** |         **-** |
| Optimized |  100 |   189.98 ns | 0.0604 ns | 0.0565 ns |   189.99 ns |     - |     - |     - |         - |
|    **Common** | **1000** | **4,332.33 ns** | **9.0642 ns** | **8.4787 ns** | **4,332.33 ns** |     **-** |     **-** |     **-** |         **-** |
| Optimized | 1000 | 1,818.46 ns | 1.5046 ns | 1.4074 ns | 1,817.79 ns |     - |     - |     - |         - |
