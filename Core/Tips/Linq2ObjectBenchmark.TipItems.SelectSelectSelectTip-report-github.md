``` ini

BenchmarkDotNet=v0.11.5, OS=Windows 10.0.14393.2999 (1607/AnniversaryUpdate/Redstone1)
Intel Core i5-8500 CPU 3.00GHz (Coffee Lake), 1 CPU, 6 logical and 6 physical cores
Frequency=2929684 Hz, Resolution=341.3337 ns, Timer=TSC
.NET Core SDK=2.2.105
  [Host] : .NET Core 2.2.3 (CoreCLR 4.6.27414.05, CoreFX 4.6.27414.05), 64bit RyuJIT
  Core   : .NET Core 2.2.3 (CoreCLR 4.6.27414.05, CoreFX 4.6.27414.05), 64bit RyuJIT

Job=Core  Runtime=Core  

```
|      Method |    N |        Mean |      Error |     StdDev |      Median |   Gen 0 |  Gen 1 | Gen 2 | Allocated |
|------------ |----- |------------:|-----------:|-----------:|------------:|--------:|-------:|------:|----------:|
|      **Common** |   **10** |    **600.7 ns** |  **1.2453 ns** |  **1.1648 ns** |    **601.0 ns** |  **0.2518** |      **-** |     **-** |    **1192 B** |
| Optimized_1 |   10 |    449.0 ns |  0.7847 ns |  0.6553 ns |    449.1 ns |  0.1812 |      - |     - |     856 B |
| Optimized_2 |   10 |    363.1 ns |  0.4879 ns |  0.4564 ns |    363.2 ns |  0.2065 |      - |     - |     976 B |
|      **Common** |  **100** |  **3,925.5 ns** |  **7.2315 ns** |  **6.7644 ns** |  **3,924.1 ns** |  **1.6251** |      **-** |     **-** |    **7672 B** |
| Optimized_1 |  100 |  3,338.5 ns |  6.4674 ns |  6.0496 ns |  3,339.4 ns |  1.5526 |      - |     - |    7336 B |
| Optimized_2 |  100 |  3,003.1 ns |  3.9206 ns |  3.6674 ns |  3,002.9 ns |  1.8196 |      - |     - |    8600 B |
|      **Common** | **1000** | **38,439.4 ns** | **81.5673 ns** | **72.3073 ns** | **38,435.6 ns** | **15.3198** | **0.0610** |     **-** |   **72472 B** |
| Optimized_1 | 1000 | 33,691.0 ns | 65.5696 ns | 61.3339 ns | 33,705.8 ns | 15.2588 | 0.0610 |     - |   72136 B |
| Optimized_2 | 1000 | 29,504.5 ns | 72.0618 ns | 67.4066 ns | 29,485.4 ns | 17.0593 |      - |     - |   80608 B |