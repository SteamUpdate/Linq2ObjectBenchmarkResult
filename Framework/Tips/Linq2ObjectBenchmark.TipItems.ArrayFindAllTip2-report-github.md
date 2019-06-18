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
|    **Common** |   **10** |    **222.9 ns** |  **0.2382 ns** |  **0.2228 ns** |    **222.9 ns** |      **0.0558** |           **-** |           **-** |               **264 B** |
| Optimized |   10 |    103.8 ns |  0.1232 ns |  0.1092 ns |    103.7 ns |      0.0525 |           - |           - |               248 B |
|    **Common** |  **100** |  **1,207.0 ns** |  **1.8066 ns** |  **1.6015 ns** |  **1,206.9 ns** |      **0.3357** |           **-** |           **-** |              **1592 B** |
| Optimized |  100 |    651.8 ns |  0.9816 ns |  0.9181 ns |    651.3 ns |      0.3338 |           - |           - |              1576 B |
|    **Common** | **1000** | **10,066.6 ns** | **22.4453 ns** | **20.9953 ns** | **10,066.3 ns** |      **2.6245** |           **-** |           **-** |             **12435 B** |
| Optimized | 1000 |  5,272.7 ns | 21.9314 ns | 20.5147 ns |  5,269.6 ns |      2.6245 |           - |           - |             12417 B |
