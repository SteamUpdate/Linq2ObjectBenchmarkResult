``` ini

BenchmarkDotNet=v0.11.5, OS=Windows 10.0.14393.2999 (1607/AnniversaryUpdate/Redstone1)
Intel Core i5-8500 CPU 3.00GHz (Coffee Lake), 1 CPU, 6 logical and 6 physical cores
Frequency=2929684 Hz, Resolution=341.3337 ns, Timer=TSC
.NET Core SDK=2.2.105
  [Host] : .NET Core 2.2.3 (CoreCLR 4.6.27414.05, CoreFX 4.6.27414.05), 64bit RyuJIT
  Core   : .NET Core 2.2.3 (CoreCLR 4.6.27414.05, CoreFX 4.6.27414.05), 64bit RyuJIT

Job=Core  Runtime=Core  

```
|    Method |    N |        Mean |      Error |    StdDev |      Median |  Gen 0 |  Gen 1 | Gen 2 | Allocated |
|---------- |----- |------------:|-----------:|----------:|------------:|-------:|-------:|------:|----------:|
|    **Common** |   **10** |    **79.34 ns** |  **0.1132 ns** | **0.1059 ns** |    **79.28 ns** | **0.0712** |      **-** |     **-** |     **336 B** |
| Optimized |   10 |    39.39 ns |  0.0469 ns | 0.0392 ns |    39.39 ns | 0.0305 |      - |     - |     144 B |
|    **Common** |  **100** |   **384.67 ns** |  **0.8409 ns** | **0.7454 ns** |   **384.75 ns** | **0.4659** |      **-** |     **-** |    **2200 B** |
| Optimized |  100 |   222.42 ns |  0.4014 ns | 0.3558 ns |   222.35 ns | 0.1829 |      - |     - |     864 B |
|    **Common** | **1000** | **2,481.29 ns** |  **7.5843 ns** | **7.0943 ns** | **2,480.29 ns** | **3.5210** |      **-** |     **-** |   **16608 B** |
| Optimized | 1000 | 1,862.83 ns | 10.0322 ns | 9.3842 ns | 1,863.89 ns | 1.7052 | 0.0019 |     - |    8064 B |
