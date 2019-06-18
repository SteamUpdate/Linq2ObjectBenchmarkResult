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
|    **Common** |   **10** |   **2.610 ns** | **0.0124 ns** | **0.0104 ns** |   **2.606 ns** |     **-** |     **-** |     **-** |         **-** |
| Optimized |   10 |   2.263 ns | 0.0088 ns | 0.0082 ns |   2.262 ns |     - |     - |     - |         - |
|    **Common** |  **100** |  **33.288 ns** | **0.0349 ns** | **0.0326 ns** |  **33.287 ns** |     **-** |     **-** |     **-** |         **-** |
| Optimized |  100 |  42.527 ns | 0.1177 ns | 0.1101 ns |  42.523 ns |     - |     - |     - |         - |
|    **Common** | **1000** | **264.863 ns** | **1.6998 ns** | **1.4194 ns** | **265.218 ns** |     **-** |     **-** |     **-** |         **-** |
| Optimized | 1000 | 278.500 ns | 0.5820 ns | 0.5444 ns | 278.753 ns |     - |     - |     - |         - |
