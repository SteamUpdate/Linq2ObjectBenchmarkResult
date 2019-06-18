``` ini

BenchmarkDotNet=v0.11.4, OS=Windows 10.0.14393.2941 (1607/AnniversaryUpdate/Redstone1)
Intel Core i5-8500 CPU 3.00GHz (Coffee Lake), 1 CPU, 6 logical and 6 physical cores
Frequency=2929686 Hz, Resolution=341.3335 ns, Timer=TSC
  [Host] : .NET Framework 4.7.2 (CLR 4.0.30319.42000), 64bit RyuJIT-v4.7.3394.0
  Clr    : .NET Framework 4.7.2 (CLR 4.0.30319.42000), 64bit RyuJIT-v4.7.3394.0

Job=Clr  Runtime=Clr  

```
|      Method |    N |         Mean |       Error |      StdDev |       Median | Gen 0/1k Op | Gen 1/1k Op | Gen 2/1k Op | Allocated Memory/Op |
|------------ |----- |-------------:|------------:|------------:|-------------:|------------:|------------:|------------:|--------------------:|
|      **Common** |   **10** |    **293.49 ns** |   **5.9185 ns** |   **8.6753 ns** |    **290.56 ns** |      **0.0949** |           **-** |           **-** |               **448 B** |
| Optimized_1 |   10 |    155.57 ns |   0.9930 ns |   0.8292 ns |    155.61 ns |      0.0236 |           - |           - |               112 B |
| Optimized_2 |   10 |     65.45 ns |   0.8684 ns |   0.7698 ns |     65.53 ns |      0.0085 |           - |           - |                40 B |
|      **Common** |  **100** |  **1,390.78 ns** |  **14.5667 ns** |  **13.6257 ns** |  **1,390.49 ns** |      **0.0935** |           **-** |           **-** |               **448 B** |
| Optimized_1 |  100 |    828.93 ns |   7.6833 ns |   6.8110 ns |    829.67 ns |      0.0229 |           - |           - |               112 B |
| Optimized_2 |  100 |    482.63 ns |   2.0804 ns |   1.8442 ns |    482.54 ns |      0.0076 |           - |           - |                40 B |
|      **Common** | **1000** | **13,927.58 ns** | **141.0674 ns** | **131.9545 ns** | **13,931.79 ns** |      **0.0916** |           **-** |           **-** |               **448 B** |
| Optimized_1 | 1000 |  8,897.59 ns |  57.0175 ns |  53.3342 ns |  8,919.82 ns |      0.0153 |           - |           - |               112 B |
| Optimized_2 | 1000 |  6,083.16 ns |  36.5927 ns |  32.4385 ns |  6,088.27 ns |      0.0076 |           - |           - |                40 B |
