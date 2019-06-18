``` ini

BenchmarkDotNet=v0.11.5, OS=Windows 10.0.14393.2999 (1607/AnniversaryUpdate/Redstone1)
Intel Core i5-8500 CPU 3.00GHz (Coffee Lake), 1 CPU, 6 logical and 6 physical cores
Frequency=2929684 Hz, Resolution=341.3337 ns, Timer=TSC
.NET Core SDK=2.2.105
  [Host] : .NET Core 2.2.3 (CoreCLR 4.6.27414.05, CoreFX 4.6.27414.05), 64bit RyuJIT
  Core   : .NET Core 2.2.3 (CoreCLR 4.6.27414.05, CoreFX 4.6.27414.05), 64bit RyuJIT

Job=Core  Runtime=Core  

```
|    Method |    N |        Mean |      Error |     StdDev |      Median |  Gen 0 |  Gen 1 | Gen 2 | Allocated |
|---------- |----- |------------:|-----------:|-----------:|------------:|-------:|-------:|------:|----------:|
|    **Common** |   **10** |    **320.8 ns** |  **0.4999 ns** |  **0.4676 ns** |    **320.9 ns** | **0.0863** |      **-** |     **-** |     **408 B** |
| Optimized |   10 |    130.5 ns |  0.2412 ns |  0.2256 ns |    130.5 ns | 0.0710 |      - |     - |     336 B |
|    **Common** |  **100** |  **1,766.5 ns** |  **1.4930 ns** |  **1.3965 ns** |  **1,766.8 ns** | **0.4807** |      **-** |     **-** |    **2272 B** |
| Optimized |  100 |    770.0 ns |  2.2058 ns |  2.0633 ns |    770.3 ns | 0.4654 |      - |     - |    2200 B |
|    **Common** | **1000** | **14,787.8 ns** | **19.7268 ns** | **18.4525 ns** | **14,785.7 ns** | **3.5248** |      **-** |     **-** |   **16680 B** |
| Optimized | 1000 |  5,682.9 ns | 21.0274 ns | 19.6690 ns |  5,679.8 ns | 3.5172 | 0.0076 |     - |   16608 B |
