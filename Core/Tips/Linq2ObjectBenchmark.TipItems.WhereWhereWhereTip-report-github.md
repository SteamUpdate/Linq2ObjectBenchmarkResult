``` ini

BenchmarkDotNet=v0.11.5, OS=Windows 10.0.14393.2999 (1607/AnniversaryUpdate/Redstone1)
Intel Core i5-8500 CPU 3.00GHz (Coffee Lake), 1 CPU, 6 logical and 6 physical cores
Frequency=2929684 Hz, Resolution=341.3337 ns, Timer=TSC
.NET Core SDK=2.2.105
  [Host] : .NET Core 2.2.3 (CoreCLR 4.6.27414.05, CoreFX 4.6.27414.05), 64bit RyuJIT
  Core   : .NET Core 2.2.3 (CoreCLR 4.6.27414.05, CoreFX 4.6.27414.05), 64bit RyuJIT

Job=Core  Runtime=Core  

```
|      Method |    N |         Mean |      Error |     StdDev |       Median |  Gen 0 | Gen 1 | Gen 2 | Allocated |
|------------ |----- |-------------:|-----------:|-----------:|-------------:|-------:|------:|------:|----------:|
|      **Common** |   **10** |    **439.89 ns** |  **0.4575 ns** |  **0.4280 ns** |    **439.82 ns** | **0.0949** |     **-** |     **-** |     **448 B** |
| Optimized_1 |   10 |    208.02 ns |  0.2193 ns |  0.2051 ns |    207.99 ns | 0.0236 |     - |     - |     112 B |
| Optimized_2 |   10 |     79.62 ns |  0.1172 ns |  0.1096 ns |     79.65 ns | 0.0085 |     - |     - |      40 B |
|      **Common** |  **100** |  **1,844.59 ns** |  **3.5650 ns** |  **3.3347 ns** |  **1,844.14 ns** | **0.0935** |     **-** |     **-** |     **448 B** |
| Optimized_1 |  100 |  1,095.61 ns |  0.6318 ns |  0.5910 ns |  1,095.38 ns | 0.0229 |     - |     - |     112 B |
| Optimized_2 |  100 |    523.51 ns |  2.8304 ns |  2.6475 ns |    523.24 ns | 0.0076 |     - |     - |      40 B |
|      **Common** | **1000** | **18,655.93 ns** | **14.1385 ns** | **13.2251 ns** | **18,652.63 ns** | **0.0916** |     **-** |     **-** |     **448 B** |
| Optimized_1 | 1000 | 12,840.22 ns |  9.1539 ns |  8.1147 ns | 12,838.40 ns | 0.0153 |     - |     - |     112 B |
| Optimized_2 | 1000 |  7,904.85 ns | 14.7953 ns | 13.1156 ns |  7,902.47 ns |      - |     - |     - |      40 B |