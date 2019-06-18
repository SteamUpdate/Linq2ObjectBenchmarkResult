``` ini

BenchmarkDotNet=v0.11.5, OS=Windows 10.0.14393.2999 (1607/AnniversaryUpdate/Redstone1)
Intel Core i5-8500 CPU 3.00GHz (Coffee Lake), 1 CPU, 6 logical and 6 physical cores
Frequency=2929684 Hz, Resolution=341.3337 ns, Timer=TSC
.NET Core SDK=2.2.105
  [Host] : .NET Core 2.2.3 (CoreCLR 4.6.27414.05, CoreFX 4.6.27414.05), 64bit RyuJIT
  Core   : .NET Core 2.2.3 (CoreCLR 4.6.27414.05, CoreFX 4.6.27414.05), 64bit RyuJIT

Job=Core  Runtime=Core  

```
|    Method |    N |         Mean |      Error |     StdDev |       Median |          Min |          Max | Rank |  Gen 0 | Gen 1 | Gen 2 | Allocated |
|---------- |----- |-------------:|-----------:|-----------:|-------------:|-------------:|-------------:|-----:|-------:|------:|------:|----------:|
|      **List** |   **10** |    **141.74 ns** |  **0.1997 ns** |  **0.1868 ns** |    **141.73 ns** |    **141.45 ns** |    **142.06 ns** |    **2** | **0.0083** |     **-** |     **-** |      **40 B** |
| HashedSet |   10 |    146.49 ns |  0.0846 ns |  0.0750 ns |    146.49 ns |    146.36 ns |    146.59 ns |    3 | 0.0083 |     - |     - |      40 B |
|     Array |   10 |     97.72 ns |  0.1104 ns |  0.0922 ns |     97.68 ns |     97.62 ns |     97.96 ns |    1 | 0.0067 |     - |     - |      32 B |
|      **List** |  **100** |  **1,120.51 ns** |  **2.1038 ns** |  **1.9679 ns** |  **1,119.67 ns** |  **1,117.94 ns** |  **1,124.82 ns** |    **5** | **0.0076** |     **-** |     **-** |      **40 B** |
| HashedSet |  100 |  1,151.05 ns | 10.7061 ns | 10.0145 ns |  1,152.86 ns |  1,132.99 ns |  1,169.73 ns |    6 | 0.0076 |     - |     - |      40 B |
|     Array |  100 |    749.45 ns |  0.6816 ns |  0.6042 ns |    749.37 ns |    748.50 ns |    750.59 ns |    4 | 0.0067 |     - |     - |      32 B |
|      **List** | **1000** | **10,910.10 ns** | **56.4621 ns** | **50.0522 ns** | **10,892.91 ns** | **10,870.98 ns** | **11,027.52 ns** |    **8** |      **-** |     **-** |     **-** |      **40 B** |
| HashedSet | 1000 | 11,150.93 ns | 99.5680 ns | 93.1359 ns | 11,148.70 ns | 10,995.15 ns | 11,298.02 ns |    9 |      - |     - |     - |      40 B |
|     Array | 1000 |  7,284.77 ns |  3.4537 ns |  3.0616 ns |  7,284.61 ns |  7,279.37 ns |  7,290.34 ns |    7 |      - |     - |     - |      32 B |