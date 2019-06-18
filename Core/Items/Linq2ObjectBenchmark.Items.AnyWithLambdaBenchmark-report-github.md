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
|      **List** |   **10** | **25.31 ns** | **0.0615 ns** | **0.0575 ns** | **25.31 ns** | **25.19 ns** | **25.43 ns** |    **3** | **0.0085** |     **-** |     **-** |      **40 B** |
| HashedSet |   10 | 27.36 ns | 0.0543 ns | 0.0508 ns | 27.38 ns | 27.22 ns | 27.43 ns |    4 | 0.0085 |     - |     - |      40 B |
|     Array |   10 | 21.39 ns | 0.0206 ns | 0.0183 ns | 21.39 ns | 21.36 ns | 21.42 ns |    1 | 0.0068 |     - |     - |      32 B |
|      **List** |  **100** | **25.57 ns** | **0.0445 ns** | **0.0416 ns** | **25.58 ns** | **25.48 ns** | **25.63 ns** |    **3** | **0.0085** |     **-** |     **-** |      **40 B** |
| HashedSet |  100 | 27.35 ns | 0.0213 ns | 0.0199 ns | 27.35 ns | 27.31 ns | 27.38 ns |    4 | 0.0085 |     - |     - |      40 B |
|     Array |  100 | 21.43 ns | 0.0186 ns | 0.0165 ns | 21.43 ns | 21.41 ns | 21.47 ns |    1 | 0.0068 |     - |     - |      32 B |
|      **List** | **1000** | **25.69 ns** | **0.0440 ns** | **0.0412 ns** | **25.68 ns** | **25.62 ns** | **25.76 ns** |    **3** | **0.0085** |     **-** |     **-** |      **40 B** |
| HashedSet | 1000 | 27.65 ns | 0.0510 ns | 0.0477 ns | 27.64 ns | 27.58 ns | 27.73 ns |    4 | 0.0085 |     - |     - |      40 B |
|     Array | 1000 | 23.92 ns | 0.0344 ns | 0.0321 ns | 23.92 ns | 23.88 ns | 23.98 ns |    2 | 0.0068 |     - |     - |      32 B |
