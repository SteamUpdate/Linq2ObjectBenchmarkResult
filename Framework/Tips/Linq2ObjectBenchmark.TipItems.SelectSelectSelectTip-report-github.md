``` ini

BenchmarkDotNet=v0.11.4, OS=Windows 10.0.14393.2999 (1607/AnniversaryUpdate/Redstone1)
Intel Core i5-8500 CPU 3.00GHz (Coffee Lake), 1 CPU, 6 logical and 6 physical cores
Frequency=2929684 Hz, Resolution=341.3337 ns, Timer=TSC
  [Host] : .NET Framework 4.7.2 (CLR 4.0.30319.42000), 64bit RyuJIT-v4.7.3416.0
  Clr    : .NET Framework 4.7.2 (CLR 4.0.30319.42000), 64bit RyuJIT-v4.7.3416.0

Job=Clr  Runtime=Clr  

```
|      Method |    N |        Mean |       Error |     StdDev |      Median | Gen 0/1k Op | Gen 1/1k Op | Gen 2/1k Op | Allocated Memory/Op |
|------------ |----- |------------:|------------:|-----------:|------------:|------------:|------------:|------------:|--------------------:|
|      **Common** |   **10** |  **1,075.0 ns** |   **1.4270 ns** |  **1.3348 ns** |  **1,074.6 ns** |      **0.2975** |           **-** |           **-** |              **1408 B** |
| Optimized_1 |   10 |    879.9 ns |   0.8565 ns |  0.8012 ns |    879.7 ns |      0.2232 |           - |           - |              1056 B |
| Optimized_2 |   10 |    691.0 ns |   1.1402 ns |  1.0665 ns |    690.8 ns |      0.2060 |           - |           - |               976 B |
|      **Common** |  **100** |  **7,710.9 ns** |  **23.9494 ns** | **22.4023 ns** |  **7,705.7 ns** |      **1.9073** |           **-** |           **-** |              **9032 B** |
| Optimized_1 |  100 |  7,310.1 ns |  15.3154 ns | 14.3260 ns |  7,309.2 ns |      1.8387 |           - |           - |              8680 B |
| Optimized_2 |  100 |  5,896.0 ns |   6.8406 ns |  6.3987 ns |  5,896.1 ns |      1.8158 |           - |           - |              8600 B |
|      **Common** | **1000** | **75,164.2 ns** |  **63.0916 ns** | **59.0159 ns** | **75,148.9 ns** |     **17.0898** |      **0.1221** |           **-** |             **81041 B** |
| Optimized_1 | 1000 | 69,655.2 ns | 105.6983 ns | 98.8703 ns | 69,637.6 ns |     17.0898 |      0.1221 |           - |             80689 B |
| Optimized_2 | 1000 | 58,567.9 ns |  61.2343 ns | 57.2786 ns | 58,558.6 ns |     17.0288 |           - |           - |             80609 B |
