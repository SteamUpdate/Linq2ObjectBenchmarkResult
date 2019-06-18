``` ini

BenchmarkDotNet=v0.11.4, OS=Windows 10.0.14393.2999 (1607/AnniversaryUpdate/Redstone1)
Intel Core i5-8500 CPU 3.00GHz (Coffee Lake), 1 CPU, 6 logical and 6 physical cores
Frequency=2929684 Hz, Resolution=341.3337 ns, Timer=TSC
  [Host] : .NET Framework 4.7.2 (CLR 4.0.30319.42000), 64bit RyuJIT-v4.7.3416.0
  Clr    : .NET Framework 4.7.2 (CLR 4.0.30319.42000), 64bit RyuJIT-v4.7.3416.0

Job=Clr  Runtime=Clr  

```
|    Method |    N |         Mean |      Error |     StdDev |       Median | Gen 0/1k Op | Gen 1/1k Op | Gen 2/1k Op | Allocated Memory/Op |
|---------- |----- |-------------:|-----------:|-----------:|-------------:|------------:|------------:|------------:|--------------------:|
|    **Common** |   **10** |    **372.14 ns** |  **0.4605 ns** |  **0.4308 ns** |    **372.16 ns** |      **0.0405** |           **-** |           **-** |               **192 B** |
| Optimized |   10 |     43.29 ns |  0.0582 ns |  0.0515 ns |     43.30 ns |      0.0085 |           - |           - |                40 B |
|    **Common** |  **100** |  **2,667.38 ns** |  **6.4513 ns** |  **5.7189 ns** |  **2,667.76 ns** |      **0.0381** |           **-** |           **-** |               **192 B** |
| Optimized |  100 |    272.37 ns |  0.4963 ns |  0.4642 ns |    272.25 ns |      0.0081 |           - |           - |                40 B |
|    **Common** | **1000** | **27,097.16 ns** | **22.0288 ns** | **20.6058 ns** | **27,098.46 ns** |      **0.0305** |           **-** |           **-** |               **248 B** |
| Optimized | 1000 |  4,224.33 ns |  7.2054 ns |  6.3874 ns |  4,223.68 ns |      0.0153 |           - |           - |                96 B |
