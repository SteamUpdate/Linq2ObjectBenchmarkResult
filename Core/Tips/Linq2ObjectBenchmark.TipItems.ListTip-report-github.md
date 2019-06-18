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
|    **Common** |   **10** |    **39.56 ns** | **0.0896 ns** | **0.0838 ns** |    **39.55 ns** |     **-** |     **-** |     **-** |         **-** |
| Optimized |   10 |    10.26 ns | 0.0078 ns | 0.0073 ns |    10.26 ns |     - |     - |     - |         - |
|    **Common** |  **100** |   **315.84 ns** | **0.3276 ns** | **0.2904 ns** |   **315.79 ns** |     **-** |     **-** |     **-** |         **-** |
| Optimized |  100 |    85.40 ns | 0.2113 ns | 0.1976 ns |    85.40 ns |     - |     - |     - |         - |
|    **Common** | **1000** | **3,225.08 ns** | **3.6638 ns** | **3.4271 ns** | **3,223.90 ns** |     **-** |     **-** |     **-** |         **-** |
| Optimized | 1000 |   782.07 ns | 1.2008 ns | 1.1233 ns |   781.73 ns |     - |     - |     - |         - |
