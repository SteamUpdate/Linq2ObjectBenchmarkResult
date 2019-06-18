``` ini

BenchmarkDotNet=v0.11.5, OS=Windows 10.0.14393.2999 (1607/AnniversaryUpdate/Redstone1)
Intel Core i5-8500 CPU 3.00GHz (Coffee Lake), 1 CPU, 6 logical and 6 physical cores
Frequency=2929684 Hz, Resolution=341.3337 ns, Timer=TSC
.NET Core SDK=2.2.105
  [Host] : .NET Core 2.2.3 (CoreCLR 4.6.27414.05, CoreFX 4.6.27414.05), 64bit RyuJIT
  Core   : .NET Core 2.2.3 (CoreCLR 4.6.27414.05, CoreFX 4.6.27414.05), 64bit RyuJIT

Job=Core  Runtime=Core  

```
|    Method |    N |       Mean |     Error |    StdDev |     Median |        Min |        Max | Rank |  Gen 0 | Gen 1 | Gen 2 | Allocated |
|---------- |----- |-----------:|----------:|----------:|-----------:|-----------:|-----------:|-----:|-------:|------:|------:|----------:|
|      **List** |   **10** | **10.7888 ns** | **0.0273 ns** | **0.0242 ns** | **10.7902 ns** | **10.7521 ns** | **10.8298 ns** |    **2** |      **-** |     **-** |     **-** |         **-** |
| HashedSet |   10 | 17.7502 ns | 0.0173 ns | 0.0153 ns | 17.7506 ns | 17.7189 ns | 17.7763 ns |    3 | 0.0085 |     - |     - |      40 B |
|     Array |   10 |  0.4612 ns | 0.0021 ns | 0.0019 ns |  0.4608 ns |  0.4585 ns |  0.4644 ns |    1 |      - |     - |     - |         - |
|      **List** |  **100** | **10.7810 ns** | **0.0136 ns** | **0.0128 ns** | **10.7792 ns** | **10.7531 ns** | **10.8011 ns** |    **2** |      **-** |     **-** |     **-** |         **-** |
| HashedSet |  100 | 18.3316 ns | 0.3287 ns | 0.3075 ns | 18.3851 ns | 17.8429 ns | 18.7641 ns |    4 | 0.0085 |     - |     - |      40 B |
|     Array |  100 |  0.4628 ns | 0.0023 ns | 0.0019 ns |  0.4621 ns |  0.4608 ns |  0.4679 ns |    1 |      - |     - |     - |         - |
|      **List** | **1000** | **10.7801 ns** | **0.0105 ns** | **0.0099 ns** | **10.7811 ns** | **10.7531 ns** | **10.7916 ns** |    **2** |      **-** |     **-** |     **-** |         **-** |
| HashedSet | 1000 | 17.8532 ns | 0.0620 ns | 0.0580 ns | 17.8487 ns | 17.7401 ns | 17.9445 ns |    3 | 0.0085 |     - |     - |      40 B |
|     Array | 1000 |  0.4625 ns | 0.0024 ns | 0.0020 ns |  0.4619 ns |  0.4599 ns |  0.4672 ns |    1 |      - |     - |     - |         - |
