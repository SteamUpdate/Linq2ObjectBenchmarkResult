``` ini

BenchmarkDotNet=v0.11.4, OS=Windows 10.0.14393.2999 (1607/AnniversaryUpdate/Redstone1)
Intel Core i5-8500 CPU 3.00GHz (Coffee Lake), 1 CPU, 6 logical and 6 physical cores
Frequency=2929684 Hz, Resolution=341.3337 ns, Timer=TSC
  [Host] : .NET Framework 4.7.2 (CLR 4.0.30319.42000), 64bit RyuJIT-v4.7.3416.0
  Clr    : .NET Framework 4.7.2 (CLR 4.0.30319.42000), 64bit RyuJIT-v4.7.3416.0

Job=Clr  Runtime=Clr  

```
|    Method |    N |        Mean |      Error |     StdDev |      Median | Gen 0/1k Op | Gen 1/1k Op | Gen 2/1k Op | Allocated Memory/Op |
|---------- |----- |------------:|-----------:|-----------:|------------:|------------:|------------:|------------:|--------------------:|
|    **Common** |   **10** |   **100.70 ns** |  **0.2630 ns** |  **0.2331 ns** |   **100.65 ns** |      **0.0712** |           **-** |           **-** |               **336 B** |
| Optimized |   10 |    44.98 ns |  0.0717 ns |  0.0671 ns |    44.96 ns |      0.0305 |           - |           - |               144 B |
|    **Common** |  **100** |   **495.96 ns** |  **0.7462 ns** |  **0.6615 ns** |   **495.93 ns** |      **0.4654** |           **-** |           **-** |              **2200 B** |
| Optimized |  100 |   302.17 ns |  0.9547 ns |  0.8930 ns |   302.61 ns |      0.1826 |           - |           - |               864 B |
|    **Common** | **1000** | **3,502.66 ns** | **12.6133 ns** | **10.5327 ns** | **3,505.38 ns** |      **3.5210** |           **-** |           **-** |             **16620 B** |
| Optimized | 1000 | 2,798.92 ns |  7.9445 ns |  6.6340 ns | 2,796.66 ns |      1.7052 |      0.0038 |           - |              8066 B |
