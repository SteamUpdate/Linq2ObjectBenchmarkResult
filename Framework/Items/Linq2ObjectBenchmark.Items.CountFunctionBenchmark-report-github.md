``` ini

BenchmarkDotNet=v0.11.4, OS=Windows 10.0.14393.2999 (1607/AnniversaryUpdate/Redstone1)
Intel Core i5-8500 CPU 3.00GHz (Coffee Lake), 1 CPU, 6 logical and 6 physical cores
Frequency=2929684 Hz, Resolution=341.3337 ns, Timer=TSC
  [Host] : .NET Framework 4.7.2 (CLR 4.0.30319.42000), 64bit RyuJIT-v4.7.3416.0
  Clr    : .NET Framework 4.7.2 (CLR 4.0.30319.42000), 64bit RyuJIT-v4.7.3416.0

Job=Clr  Runtime=Clr  

```
|    Method |    N |      Mean |     Error |    StdDev |    Median |       Min |       Max | Rank | Gen 0/1k Op | Gen 1/1k Op | Gen 2/1k Op | Allocated Memory/Op |
|---------- |----- |----------:|----------:|----------:|----------:|----------:|----------:|-----:|------------:|------------:|------------:|--------------------:|
|      **List** |   **10** |  **4.617 ns** | **0.0061 ns** | **0.0057 ns** |  **4.616 ns** |  **4.608 ns** |  **4.628 ns** |    **1** |           **-** |           **-** |           **-** |                   **-** |
| HashedSet |   10 |  5.140 ns | 0.0081 ns | 0.0076 ns |  5.139 ns |  5.128 ns |  5.155 ns |    2 |           - |           - |           - |                   - |
|     Array |   10 | 24.654 ns | 0.0560 ns | 0.0523 ns | 24.658 ns | 24.588 ns | 24.759 ns |    3 |           - |           - |           - |                   - |
|      **List** |  **100** |  **4.607 ns** | **0.0087 ns** | **0.0077 ns** |  **4.610 ns** |  **4.591 ns** |  **4.617 ns** |    **1** |           **-** |           **-** |           **-** |                   **-** |
| HashedSet |  100 |  5.144 ns | 0.0102 ns | 0.0095 ns |  5.140 ns |  5.133 ns |  5.163 ns |    2 |           - |           - |           - |                   - |
|     Array |  100 | 24.622 ns | 0.0827 ns | 0.0774 ns | 24.597 ns | 24.542 ns | 24.786 ns |    3 |           - |           - |           - |                   - |
|      **List** | **1000** |  **4.616 ns** | **0.0095 ns** | **0.0084 ns** |  **4.617 ns** |  **4.604 ns** |  **4.633 ns** |    **1** |           **-** |           **-** |           **-** |                   **-** |
| HashedSet | 1000 |  5.145 ns | 0.0069 ns | 0.0064 ns |  5.146 ns |  5.134 ns |  5.159 ns |    2 |           - |           - |           - |                   - |
|     Array | 1000 | 24.703 ns | 0.0347 ns | 0.0290 ns | 24.708 ns | 24.643 ns | 24.744 ns |    3 |           - |           - |           - |                   - |
