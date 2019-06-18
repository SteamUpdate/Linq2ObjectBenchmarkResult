``` ini

BenchmarkDotNet=v0.11.5, OS=Windows 10.0.14393.2999 (1607/AnniversaryUpdate/Redstone1)
Intel Core i5-8500 CPU 3.00GHz (Coffee Lake), 1 CPU, 6 logical and 6 physical cores
Frequency=2929684 Hz, Resolution=341.3337 ns, Timer=TSC
.NET Core SDK=2.2.105
  [Host] : .NET Core 2.2.3 (CoreCLR 4.6.27414.05, CoreFX 4.6.27414.05), 64bit RyuJIT
  Core   : .NET Core 2.2.3 (CoreCLR 4.6.27414.05, CoreFX 4.6.27414.05), 64bit RyuJIT

Job=Core  Runtime=Core  

```
|    Method |    N |         Mean |     Error |    StdDev |       Median |  Gen 0 | Gen 1 | Gen 2 | Allocated |
|---------- |----- |-------------:|----------:|----------:|-------------:|-------:|------:|------:|----------:|
|    **Common** |   **10** |    **141.35 ns** | **0.3575 ns** | **0.3344 ns** |    **141.43 ns** | **0.0083** |     **-** |     **-** |      **40 B** |
| Optimized |   10 |     21.73 ns | 0.0093 ns | 0.0078 ns |     21.73 ns |      - |     - |     - |         - |
|    **Common** |  **100** |  **1,100.05 ns** | **0.4273 ns** | **0.3568 ns** |  **1,099.99 ns** | **0.0076** |     **-** |     **-** |      **40 B** |
| Optimized |  100 |    213.08 ns | 0.1486 ns | 0.1317 ns |    213.08 ns |      - |     - |     - |         - |
|    **Common** | **1000** | **10,715.64 ns** | **9.8503 ns** | **9.2140 ns** | **10,712.71 ns** |      **-** |     **-** |     **-** |      **40 B** |
| Optimized | 1000 |  2,073.99 ns | 3.7034 ns | 3.4642 ns |  2,072.57 ns |      - |     - |     - |         - |
