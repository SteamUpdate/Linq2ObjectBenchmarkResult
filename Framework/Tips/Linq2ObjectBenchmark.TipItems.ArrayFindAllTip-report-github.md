``` ini

BenchmarkDotNet=v0.11.4, OS=Windows 10.0.14393.2999 (1607/AnniversaryUpdate/Redstone1)
Intel Core i5-8500 CPU 3.00GHz (Coffee Lake), 1 CPU, 6 logical and 6 physical cores
Frequency=2929684 Hz, Resolution=341.3337 ns, Timer=TSC
  [Host] : .NET Framework 4.7.2 (CLR 4.0.30319.42000), 64bit RyuJIT-v4.7.3416.0
  Clr    : .NET Framework 4.7.2 (CLR 4.0.30319.42000), 64bit RyuJIT-v4.7.3416.0

Job=Clr  Runtime=Clr  

```
|    Method |    N |        Mean |     Error |    StdDev |      Median | Gen 0/1k Op | Gen 1/1k Op | Gen 2/1k Op | Allocated Memory/Op |
|---------- |----- |------------:|----------:|----------:|------------:|------------:|------------:|------------:|--------------------:|
|    **Common** |   **10** |    **92.77 ns** | **1.8574 ns** | **1.8242 ns** |    **93.32 ns** |      **0.0169** |           **-** |           **-** |                **80 B** |
| Optimized |   10 |    44.93 ns | 0.2104 ns | 0.1968 ns |    44.86 ns |      0.0135 |           - |           - |                64 B |
|    **Common** |  **100** |   **285.78 ns** | **0.3738 ns** | **0.3497 ns** |   **285.77 ns** |      **0.0167** |           **-** |           **-** |                **80 B** |
| Optimized |  100 |   276.39 ns | 0.3129 ns | 0.2443 ns |   276.41 ns |      0.0134 |           - |           - |                64 B |
|    **Common** | **1000** | **2,333.01 ns** | **3.7651 ns** | **3.5219 ns** | **2,333.54 ns** |      **0.0267** |           **-** |           **-** |               **144 B** |
| Optimized | 1000 | 2,616.34 ns | 4.3545 ns | 3.8601 ns | 2,615.40 ns |      0.0267 |           - |           - |               128 B |
