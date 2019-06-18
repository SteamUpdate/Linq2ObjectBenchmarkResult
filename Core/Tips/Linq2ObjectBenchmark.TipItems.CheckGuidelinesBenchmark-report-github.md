``` ini

BenchmarkDotNet=v0.11.5, OS=Windows 10.0.14393.2999 (1607/AnniversaryUpdate/Redstone1)
Intel Core i5-8500 CPU 3.00GHz (Coffee Lake), 1 CPU, 6 logical and 6 physical cores
Frequency=2929684 Hz, Resolution=341.3337 ns, Timer=TSC
.NET Core SDK=2.2.105
  [Host] : .NET Core 2.2.3 (CoreCLR 4.6.27414.05, CoreFX 4.6.27414.05), 64bit RyuJIT
  Core   : .NET Core 2.2.3 (CoreCLR 4.6.27414.05, CoreFX 4.6.27414.05), 64bit RyuJIT

Job=Core  Runtime=Core  

```
|                   Method |    N |        Mean |     Error |    StdDev |      Median |  Gen 0 | Gen 1 | Gen 2 | Allocated |
|------------------------- |----- |------------:|----------:|----------:|------------:|-------:|------:|------:|----------:|
| **&#39;Array.Find with lambda&#39;** |   **10** |    **27.56 ns** | **0.1215 ns** | **0.1136 ns** |    **27.55 ns** |      **-** |     **-** |     **-** |         **-** |
|               Array.Find |   10 |    27.58 ns | 0.1255 ns | 0.1174 ns |    27.53 ns |      - |     - |     - |         - |
|           FirstOrDefault |   10 |   119.15 ns | 0.1853 ns | 0.1734 ns |   119.09 ns | 0.0067 |     - |     - |      32 B |
| **&#39;Array.Find with lambda&#39;** |  **100** |   **260.74 ns** | **0.6923 ns** | **0.5781 ns** |   **260.89 ns** |      **-** |     **-** |     **-** |         **-** |
|               Array.Find |  100 |   264.78 ns | 4.3699 ns | 4.0876 ns |   265.43 ns |      - |     - |     - |         - |
|           FirstOrDefault |  100 |   818.95 ns | 0.9944 ns | 0.9301 ns |   818.74 ns | 0.0067 |     - |     - |      32 B |
| **&#39;Array.Find with lambda&#39;** | **1000** | **2,515.58 ns** | **2.5403 ns** | **2.3762 ns** | **2,515.20 ns** |      **-** |     **-** |     **-** |         **-** |
|               Array.Find | 1000 | 2,518.36 ns | 3.5953 ns | 3.3630 ns | 2,518.64 ns |      - |     - |     - |         - |
|           FirstOrDefault | 1000 | 4,645.33 ns | 6.3005 ns | 5.5852 ns | 4,645.14 ns |      - |     - |     - |      32 B |
