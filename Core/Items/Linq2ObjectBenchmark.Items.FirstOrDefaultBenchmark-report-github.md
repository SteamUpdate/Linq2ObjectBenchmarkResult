``` ini

BenchmarkDotNet=v0.11.5, OS=Windows 10.0.14393.2999 (1607/AnniversaryUpdate/Redstone1)
Intel Core i5-8500 CPU 3.00GHz (Coffee Lake), 1 CPU, 6 logical and 6 physical cores
Frequency=2929684 Hz, Resolution=341.3337 ns, Timer=TSC
.NET Core SDK=2.2.105
  [Host] : .NET Core 2.2.3 (CoreCLR 4.6.27414.05, CoreFX 4.6.27414.05), 64bit RyuJIT
  Core   : .NET Core 2.2.3 (CoreCLR 4.6.27414.05, CoreFX 4.6.27414.05), 64bit RyuJIT

Job=Core  Runtime=Core  

```
|    Method |    N |     Mean |     Error |    StdDev |   Median |      Min |      Max | Rank |  Gen 0 | Gen 1 | Gen 2 | Allocated |
|---------- |----- |---------:|----------:|----------:|---------:|---------:|---------:|-----:|-------:|------:|------:|----------:|
|      **List** |   **10** | **29.69 ns** | **0.0506 ns** | **0.0448 ns** | **29.70 ns** | **29.59 ns** | **29.76 ns** |    **1** |      **-** |     **-** |     **-** |         **-** |
| HashedSet |   10 | 50.92 ns | 0.0500 ns | 0.0443 ns | 50.91 ns | 50.84 ns | 51.00 ns |    4 | 0.0085 |     - |     - |      40 B |
|     Array |   10 | 43.98 ns | 0.0467 ns | 0.0414 ns | 43.98 ns | 43.92 ns | 44.06 ns |    3 |      - |     - |     - |         - |
|      **List** |  **100** | **29.61 ns** | **0.0361 ns** | **0.0338 ns** | **29.62 ns** | **29.56 ns** | **29.66 ns** |    **1** |      **-** |     **-** |     **-** |         **-** |
| HashedSet |  100 | 50.70 ns | 0.0711 ns | 0.0630 ns | 50.71 ns | 50.59 ns | 50.80 ns |    4 | 0.0085 |     - |     - |      40 B |
|     Array |  100 | 38.39 ns | 0.0392 ns | 0.0348 ns | 38.38 ns | 38.35 ns | 38.47 ns |    2 |      - |     - |     - |         - |
|      **List** | **1000** | **29.45 ns** | **0.1568 ns** | **0.1467 ns** | **29.43 ns** | **29.27 ns** | **29.62 ns** |    **1** |      **-** |     **-** |     **-** |         **-** |
| HashedSet | 1000 | 50.60 ns | 0.0623 ns | 0.0583 ns | 50.59 ns | 50.53 ns | 50.70 ns |    4 | 0.0085 |     - |     - |      40 B |
|     Array | 1000 | 38.33 ns | 0.0274 ns | 0.0256 ns | 38.32 ns | 38.30 ns | 38.38 ns |    2 |      - |     - |     - |         - |
