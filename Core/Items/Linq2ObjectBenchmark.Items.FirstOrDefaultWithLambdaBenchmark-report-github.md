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
|      **List** |   **10** | **33.57 ns** | **0.0468 ns** | **0.0438 ns** | **33.56 ns** | **33.51 ns** | **33.64 ns** |    **2** | **0.0085** |     **-** |     **-** |      **40 B** |
| HashedSet |   10 | 36.52 ns | 0.1022 ns | 0.0956 ns | 36.46 ns | 36.40 ns | 36.66 ns |    3 | 0.0085 |     - |     - |      40 B |
|     Array |   10 | 27.64 ns | 0.0317 ns | 0.0296 ns | 27.63 ns | 27.59 ns | 27.70 ns |    1 | 0.0068 |     - |     - |      32 B |
|      **List** |  **100** | **33.48 ns** | **0.0415 ns** | **0.0368 ns** | **33.49 ns** | **33.40 ns** | **33.53 ns** |    **2** | **0.0085** |     **-** |     **-** |      **40 B** |
| HashedSet |  100 | 36.53 ns | 0.0862 ns | 0.0807 ns | 36.51 ns | 36.42 ns | 36.66 ns |    3 | 0.0085 |     - |     - |      40 B |
|     Array |  100 | 27.58 ns | 0.0474 ns | 0.0443 ns | 27.55 ns | 27.53 ns | 27.67 ns |    1 | 0.0068 |     - |     - |      32 B |
|      **List** | **1000** | **33.48 ns** | **0.0397 ns** | **0.0372 ns** | **33.48 ns** | **33.41 ns** | **33.55 ns** |    **2** | **0.0085** |     **-** |     **-** |      **40 B** |
| HashedSet | 1000 | 36.61 ns | 0.0523 ns | 0.0463 ns | 36.60 ns | 36.55 ns | 36.71 ns |    3 | 0.0085 |     - |     - |      40 B |
|     Array | 1000 | 27.65 ns | 0.0440 ns | 0.0411 ns | 27.65 ns | 27.59 ns | 27.72 ns |    1 | 0.0068 |     - |     - |      32 B |
