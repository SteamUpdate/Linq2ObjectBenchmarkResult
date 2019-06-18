``` ini

BenchmarkDotNet=v0.11.4, OS=Windows 10.0.14393.2999 (1607/AnniversaryUpdate/Redstone1)
Intel Core i5-8500 CPU 3.00GHz (Coffee Lake), 1 CPU, 6 logical and 6 physical cores
Frequency=2929684 Hz, Resolution=341.3337 ns, Timer=TSC
  [Host] : .NET Framework 4.7.2 (CLR 4.0.30319.42000), 64bit RyuJIT-v4.7.3416.0
  Clr    : .NET Framework 4.7.2 (CLR 4.0.30319.42000), 64bit RyuJIT-v4.7.3416.0

Job=Clr  Runtime=Clr  

```
|    Method |    N |        Mean |      Error |     StdDev |      Median |         Min |         Max | Rank | Gen 0/1k Op | Gen 1/1k Op | Gen 2/1k Op | Allocated Memory/Op |
|---------- |----- |------------:|-----------:|-----------:|------------:|------------:|------------:|-----:|------------:|------------:|------------:|--------------------:|
|      **List** |   **10** |    **427.6 ns** |  **1.5699 ns** |  **1.4685 ns** |    **426.9 ns** |    **426.2 ns** |    **430.5 ns** |    **1** |      **0.0911** |           **-** |           **-** |               **432 B** |
| HashedSet |   10 |    430.7 ns |  0.6061 ns |  0.5670 ns |    430.8 ns |    430.0 ns |    431.7 ns |    1 |      0.0911 |           - |           - |               432 B |
|     Array |   10 |    520.7 ns |  1.9307 ns |  1.8060 ns |    519.7 ns |    519.0 ns |    524.7 ns |    2 |      0.0896 |           - |           - |               424 B |
|      **List** |  **100** |  **2,956.1 ns** |  **4.7425 ns** |  **4.4361 ns** |  **2,956.3 ns** |  **2,949.5 ns** |  **2,964.9 ns** |    **3** |      **0.4845** |           **-** |           **-** |              **2296 B** |
| HashedSet |  100 |  3,029.1 ns |  3.7408 ns |  3.4992 ns |  3,028.9 ns |  3,022.6 ns |  3,034.6 ns |    4 |      0.4845 |           - |           - |              2296 B |
|     Array |  100 |  3,828.0 ns |  3.6643 ns |  3.2483 ns |  3,828.0 ns |  3,822.6 ns |  3,834.9 ns |    5 |      0.4807 |           - |           - |              2288 B |
|      **List** | **1000** | **26,601.1 ns** | **46.6305 ns** | **43.6182 ns** | **26,596.7 ns** | **26,529.7 ns** | **26,686.5 ns** |    **6** |      **3.5095** |           **-** |           **-** |             **16707 B** |
| HashedSet | 1000 | 27,642.5 ns | 89.8004 ns | 79.6058 ns | 27,612.3 ns | 27,574.0 ns | 27,851.0 ns |    7 |      3.5095 |           - |           - |             16707 B |
|     Array | 1000 | 35,174.5 ns | 33.9970 ns | 30.1374 ns | 35,169.3 ns | 35,141.7 ns | 35,221.9 ns |    8 |      3.4790 |           - |           - |             16702 B |