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
|    **Common** |   **10** |   **101.62 ns** |  **0.2632 ns** |  **0.2333 ns** |   **101.62 ns** | **0.0067** |     **-** |     **-** |      **32 B** |
| Optimized |   10 |    17.62 ns |  0.1033 ns |  0.0966 ns |    17.65 ns |      - |     - |     - |         - |
|    **Common** |  **100** |   **708.39 ns** |  **1.0511 ns** |  **0.8778 ns** |   **708.31 ns** | **0.0067** |     **-** |     **-** |      **32 B** |
| Optimized |  100 |   158.72 ns |  0.1832 ns |  0.1624 ns |   158.73 ns |      - |     - |     - |         - |
|    **Common** | **1000** | **3,137.16 ns** | **12.4718 ns** | **11.6661 ns** | **3,138.08 ns** | **0.0038** |     **-** |     **-** |      **32 B** |
| Optimized | 1000 |   714.38 ns |  5.1657 ns |  4.8320 ns |   714.42 ns |      - |     - |     - |         - |