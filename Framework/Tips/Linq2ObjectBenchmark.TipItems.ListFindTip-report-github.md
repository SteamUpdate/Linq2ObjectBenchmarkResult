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
|    **Common** |   **10** |    **126.81 ns** |  **0.3457 ns** |  **0.3234 ns** |    **126.85 ns** |      **0.0083** |           **-** |           **-** |                **40 B** |
| Optimized |   10 |     18.56 ns |  0.0505 ns |  0.0422 ns |     18.56 ns |           - |           - |           - |                   - |
|    **Common** |  **100** |  **1,043.15 ns** |  **2.0082 ns** |  **1.7802 ns** |  **1,042.83 ns** |      **0.0076** |           **-** |           **-** |                **40 B** |
| Optimized |  100 |    183.33 ns |  0.4473 ns |  0.4184 ns |    183.26 ns |           - |           - |           - |                   - |
|    **Common** | **1000** | **10,218.18 ns** | **37.3226 ns** | **34.9116 ns** | **10,232.77 ns** |           **-** |           **-** |           **-** |                **40 B** |
| Optimized | 1000 |  1,773.42 ns |  1.5327 ns |  1.4337 ns |  1,773.46 ns |           - |           - |           - |                   - |
