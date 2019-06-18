``` ini

BenchmarkDotNet=v0.11.5, OS=Windows 10.0.14393.2999 (1607/AnniversaryUpdate/Redstone1)
Intel Core i5-8500 CPU 3.00GHz (Coffee Lake), 1 CPU, 6 logical and 6 physical cores
Frequency=2929684 Hz, Resolution=341.3337 ns, Timer=TSC
.NET Core SDK=2.2.105
  [Host] : .NET Core 2.2.3 (CoreCLR 4.6.27414.05, CoreFX 4.6.27414.05), 64bit RyuJIT
  Core   : .NET Core 2.2.3 (CoreCLR 4.6.27414.05, CoreFX 4.6.27414.05), 64bit RyuJIT

Job=Core  Runtime=Core  

```
|    Method |    N |     Mean |     Error |    StdDev |   Median |      Min |      Max | Rank | Gen 0 | Gen 1 | Gen 2 | Allocated |
|---------- |----- |---------:|----------:|----------:|---------:|---------:|---------:|-----:|------:|------:|------:|----------:|
|      **List** |   **10** | **11.03 ns** | **0.0325 ns** | **0.0304 ns** | **11.02 ns** | **10.99 ns** | **11.09 ns** |    **1** |     **-** |     **-** |     **-** |         **-** |
| HashedSet |   10 | 11.52 ns | 0.0115 ns | 0.0108 ns | 11.52 ns | 11.50 ns | 11.54 ns |    2 |     - |     - |     - |         - |
|     Array |   10 | 18.37 ns | 0.0141 ns | 0.0125 ns | 18.37 ns | 18.36 ns | 18.39 ns |    3 |     - |     - |     - |         - |
|      **List** |  **100** | **11.01 ns** | **0.0160 ns** | **0.0150 ns** | **11.01 ns** | **10.99 ns** | **11.04 ns** |    **1** |     **-** |     **-** |     **-** |         **-** |
| HashedSet |  100 | 11.53 ns | 0.0219 ns | 0.0205 ns | 11.52 ns | 11.50 ns | 11.58 ns |    2 |     - |     - |     - |         - |
|     Array |  100 | 18.38 ns | 0.0191 ns | 0.0169 ns | 18.38 ns | 18.36 ns | 18.42 ns |    3 |     - |     - |     - |         - |
|      **List** | **1000** | **11.00 ns** | **0.0153 ns** | **0.0143 ns** | **11.00 ns** | **10.98 ns** | **11.02 ns** |    **1** |     **-** |     **-** |     **-** |         **-** |
| HashedSet | 1000 | 11.53 ns | 0.0214 ns | 0.0200 ns | 11.53 ns | 11.50 ns | 11.58 ns |    2 |     - |     - |     - |         - |
|     Array | 1000 | 18.63 ns | 0.0142 ns | 0.0126 ns | 18.63 ns | 18.59 ns | 18.64 ns |    4 |     - |     - |     - |         - |
