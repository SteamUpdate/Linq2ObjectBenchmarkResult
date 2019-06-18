``` ini

BenchmarkDotNet=v0.11.4, OS=Windows 10.0.14393.2999 (1607/AnniversaryUpdate/Redstone1)
Intel Core i5-8500 CPU 3.00GHz (Coffee Lake), 1 CPU, 6 logical and 6 physical cores
Frequency=2929684 Hz, Resolution=341.3337 ns, Timer=TSC
  [Host] : .NET Framework 4.7.2 (CLR 4.0.30319.42000), 64bit RyuJIT-v4.7.3416.0
  Clr    : .NET Framework 4.7.2 (CLR 4.0.30319.42000), 64bit RyuJIT-v4.7.3416.0

Job=Clr  Runtime=Clr  

```
|    Method |    N |     Mean |     Error |    StdDev |   Median |      Min |      Max | Rank | Gen 0/1k Op | Gen 1/1k Op | Gen 2/1k Op | Allocated Memory/Op |
|---------- |----- |---------:|----------:|----------:|---------:|---------:|---------:|-----:|------------:|------------:|------------:|--------------------:|
|      **List** |   **10** | **23.59 ns** | **0.0500 ns** | **0.0468 ns** | **23.59 ns** | **23.52 ns** | **23.70 ns** |    **2** |      **0.0085** |           **-** |           **-** |                **40 B** |
| HashedSet |   10 | 23.78 ns | 0.0374 ns | 0.0313 ns | 23.79 ns | 23.72 ns | 23.85 ns |    2 |      0.0085 |           - |           - |                40 B |
|     Array |   10 | 18.42 ns | 0.0307 ns | 0.0239 ns | 18.43 ns | 18.37 ns | 18.45 ns |    1 |      0.0068 |           - |           - |                32 B |
|      **List** |  **100** | **23.34 ns** | **0.0633 ns** | **0.0592 ns** | **23.34 ns** | **23.27 ns** | **23.46 ns** |    **2** |      **0.0085** |           **-** |           **-** |                **40 B** |
| HashedSet |  100 | 23.90 ns | 0.0860 ns | 0.0763 ns | 23.88 ns | 23.81 ns | 24.08 ns |    2 |      0.0085 |           - |           - |                40 B |
|     Array |  100 | 18.44 ns | 0.0237 ns | 0.0198 ns | 18.43 ns | 18.40 ns | 18.47 ns |    1 |      0.0068 |           - |           - |                32 B |
|      **List** | **1000** | **23.37 ns** | **0.1378 ns** | **0.1221 ns** | **23.33 ns** | **23.22 ns** | **23.61 ns** |    **2** |      **0.0085** |           **-** |           **-** |                **40 B** |
| HashedSet | 1000 | 23.70 ns | 0.0302 ns | 0.0268 ns | 23.70 ns | 23.65 ns | 23.73 ns |    2 |      0.0085 |           - |           - |                40 B |
|     Array | 1000 | 18.46 ns | 0.1172 ns | 0.1096 ns | 18.42 ns | 18.33 ns | 18.69 ns |    1 |      0.0068 |           - |           - |                32 B |
