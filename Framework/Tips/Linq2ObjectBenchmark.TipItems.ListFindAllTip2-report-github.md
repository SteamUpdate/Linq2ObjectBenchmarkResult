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
|    **Common** |   **10** |    **338.9 ns** |  **0.3751 ns** |  **0.3509 ns** |    **339.0 ns** |      **0.0863** |           **-** |           **-** |               **408 B** |
| Optimized |   10 |    135.4 ns |  0.3939 ns |  0.3685 ns |    135.5 ns |      0.0710 |           - |           - |               336 B |
|    **Common** |  **100** |  **2,028.1 ns** |  **2.3069 ns** |  **2.1579 ns** |  **2,027.5 ns** |      **0.4807** |           **-** |           **-** |              **2272 B** |
| Optimized |  100 |    814.7 ns |  1.0649 ns |  0.9961 ns |    814.8 ns |      0.4654 |           - |           - |              2200 B |
|    **Common** | **1000** | **17,577.6 ns** | **35.1812 ns** | **32.9085 ns** | **17,575.7 ns** |      **3.5095** |           **-** |           **-** |             **16692 B** |
| Optimized | 1000 |  6,393.6 ns |  9.3095 ns |  8.7081 ns |  6,394.7 ns |      3.5172 |      0.0076 |           - |             16620 B |
