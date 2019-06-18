``` ini

BenchmarkDotNet=v0.11.4, OS=Windows 10.0.14393.2999 (1607/AnniversaryUpdate/Redstone1)
Intel Core i5-8500 CPU 3.00GHz (Coffee Lake), 1 CPU, 6 logical and 6 physical cores
Frequency=2929684 Hz, Resolution=341.3337 ns, Timer=TSC
  [Host] : .NET Framework 4.7.2 (CLR 4.0.30319.42000), 64bit RyuJIT-v4.7.3416.0
  Clr    : .NET Framework 4.7.2 (CLR 4.0.30319.42000), 64bit RyuJIT-v4.7.3416.0

Job=Clr  Runtime=Clr  

```
|      Method |    N |         Mean |      Error |     StdDev |       Median | Gen 0/1k Op | Gen 1/1k Op | Gen 2/1k Op | Allocated Memory/Op |
|------------ |----- |-------------:|-----------:|-----------:|-------------:|------------:|------------:|------------:|--------------------:|
|      **Common** |   **10** |    **264.15 ns** |  **0.4749 ns** |  **0.4442 ns** |    **264.16 ns** |      **0.0949** |           **-** |           **-** |               **448 B** |
| Optimized_1 |   10 |    149.14 ns |  0.1679 ns |  0.1571 ns |    149.15 ns |      0.0236 |           - |           - |               112 B |
| Optimized_2 |   10 |     63.62 ns |  0.0778 ns |  0.0690 ns |     63.61 ns |      0.0085 |           - |           - |                40 B |
|      **Common** |  **100** |  **1,317.23 ns** |  **1.7649 ns** |  **1.5645 ns** |  **1,316.92 ns** |      **0.0935** |           **-** |           **-** |               **448 B** |
| Optimized_1 |  100 |    800.76 ns |  2.0416 ns |  1.9097 ns |    801.12 ns |      0.0229 |           - |           - |               112 B |
| Optimized_2 |  100 |    471.20 ns |  0.3636 ns |  0.3223 ns |    471.30 ns |      0.0081 |           - |           - |                40 B |
|      **Common** | **1000** | **13,481.45 ns** | **31.2210 ns** | **27.6766 ns** | **13,483.89 ns** |      **0.0916** |           **-** |           **-** |               **448 B** |
| Optimized_1 | 1000 |  8,698.36 ns | 44.1724 ns | 41.3189 ns |  8,697.41 ns |      0.0153 |           - |           - |               112 B |
| Optimized_2 | 1000 |  5,965.35 ns | 25.1982 ns | 21.0416 ns |  5,955.74 ns |      0.0076 |           - |           - |                40 B |
