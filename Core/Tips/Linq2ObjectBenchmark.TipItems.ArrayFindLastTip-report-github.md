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
|    **Common** |   **10** |    **87.58 ns** | **0.0996 ns** | **0.0832 ns** |    **87.55 ns** |     **-** |     **-** |     **-** |         **-** |
| Optimized |   10 |    17.32 ns | 0.0732 ns | 0.0649 ns |    17.30 ns |     - |     - |     - |         - |
|    **Common** |  **100** |   **572.09 ns** | **3.0006 ns** | **2.6600 ns** |   **571.15 ns** |     **-** |     **-** |     **-** |         **-** |
| Optimized |  100 |   160.63 ns | 0.7327 ns | 0.6854 ns |   160.55 ns |     - |     - |     - |         - |
|    **Common** | **1000** | **2,957.00 ns** | **9.8448 ns** | **9.2089 ns** | **2,954.64 ns** |     **-** |     **-** |     **-** |         **-** |
| Optimized | 1000 |   855.61 ns | 3.2651 ns | 2.8944 ns |   854.84 ns |     - |     - |     - |         - |
