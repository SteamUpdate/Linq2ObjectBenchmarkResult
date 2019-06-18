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
|    **Common** |   **10** |   **139.15 ns** |  **0.1746 ns** |  **0.1633 ns** |   **139.18 ns** |      **0.0236** |           **-** |           **-** |               **112 B** |
| Optimized |   10 |    31.90 ns |  0.0372 ns |  0.0348 ns |    31.90 ns |      0.0085 |           - |           - |                40 B |
|    **Common** |  **100** |   **682.86 ns** |  **0.6007 ns** |  **0.5325 ns** |   **682.73 ns** |      **0.0229** |           **-** |           **-** |               **112 B** |
| Optimized |  100 |   226.68 ns |  2.3516 ns |  2.1997 ns |   227.31 ns |      0.0083 |           - |           - |                40 B |
|    **Common** | **1000** | **6,132.72 ns** | **15.0406 ns** | **12.5596 ns** | **6,130.14 ns** |      **0.0229** |           **-** |           **-** |               **112 B** |
| Optimized | 1000 | 2,112.27 ns | 15.4235 ns | 14.4272 ns | 2,118.07 ns |      0.0076 |           - |           - |                40 B |
