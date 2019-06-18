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
|      **List** |   **10** | **16.92 ns** | **0.0310 ns** | **0.0290 ns** | **16.92 ns** | **16.85 ns** | **16.96 ns** |    **2** | **0.0085** |     **-** |     **-** |      **40 B** |
| HashedSet |   10 | 18.44 ns | 0.0289 ns | 0.0270 ns | 18.44 ns | 18.42 ns | 18.51 ns |    4 | 0.0085 |     - |     - |      40 B |
|     Array |   10 | 13.37 ns | 0.0275 ns | 0.0244 ns | 13.36 ns | 13.33 ns | 13.42 ns |    1 | 0.0068 |     - |     - |      32 B |
|      **List** |  **100** | **17.02 ns** | **0.0188 ns** | **0.0175 ns** | **17.02 ns** | **16.99 ns** | **17.06 ns** |    **2** | **0.0085** |     **-** |     **-** |      **40 B** |
| HashedSet |  100 | 18.42 ns | 0.0279 ns | 0.0261 ns | 18.41 ns | 18.37 ns | 18.46 ns |    4 | 0.0085 |     - |     - |      40 B |
|     Array |  100 | 13.15 ns | 0.0391 ns | 0.0366 ns | 13.15 ns | 13.09 ns | 13.22 ns |    1 | 0.0068 |     - |     - |      32 B |
|      **List** | **1000** | **16.90 ns** | **0.0233 ns** | **0.0218 ns** | **16.90 ns** | **16.85 ns** | **16.94 ns** |    **2** | **0.0085** |     **-** |     **-** |      **40 B** |
| HashedSet | 1000 | 18.17 ns | 0.0503 ns | 0.0471 ns | 18.16 ns | 18.11 ns | 18.27 ns |    3 | 0.0085 |     - |     - |      40 B |
|     Array | 1000 | 13.23 ns | 0.0205 ns | 0.0192 ns | 13.23 ns | 13.20 ns | 13.27 ns |    1 | 0.0068 |     - |     - |      32 B |
