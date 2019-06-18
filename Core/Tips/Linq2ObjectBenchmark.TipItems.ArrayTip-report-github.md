``` ini

BenchmarkDotNet=v0.11.5, OS=Windows 10.0.14393.2999 (1607/AnniversaryUpdate/Redstone1)
Intel Core i5-8500 CPU 3.00GHz (Coffee Lake), 1 CPU, 6 logical and 6 physical cores
Frequency=2929684 Hz, Resolution=341.3337 ns, Timer=TSC
.NET Core SDK=2.2.105
  [Host] : .NET Core 2.2.3 (CoreCLR 4.6.27414.05, CoreFX 4.6.27414.05), 64bit RyuJIT
  Core   : .NET Core 2.2.3 (CoreCLR 4.6.27414.05, CoreFX 4.6.27414.05), 64bit RyuJIT

Job=Core  Runtime=Core  

```
|    Method |    N |       Mean |     Error |    StdDev |     Median | Gen 0 | Gen 1 | Gen 2 | Allocated |
|---------- |----- |-----------:|----------:|----------:|-----------:|------:|------:|------:|----------:|
|    **Common** |   **10** |   **2.610 ns** | **0.0155 ns** | **0.0145 ns** |   **2.606 ns** |     **-** |     **-** |     **-** |         **-** |
| Optimized |   10 |   3.433 ns | 0.0101 ns | 0.0095 ns |   3.431 ns |     - |     - |     - |         - |
|    **Common** |  **100** |  **33.284 ns** | **0.0612 ns** | **0.0543 ns** |  **33.292 ns** |     **-** |     **-** |     **-** |         **-** |
| Optimized |  100 |  42.100 ns | 0.0738 ns | 0.0690 ns |  42.093 ns |     - |     - |     - |         - |
|    **Common** | **1000** | **261.166 ns** | **0.3737 ns** | **0.3313 ns** | **261.167 ns** |     **-** |     **-** |     **-** |         **-** |
| Optimized | 1000 | 276.189 ns | 1.1717 ns | 1.0960 ns | 275.680 ns |     - |     - |     - |         - |
