``` ini

BenchmarkDotNet=v0.11.4, OS=Windows 10.0.14393.2999 (1607/AnniversaryUpdate/Redstone1)
Intel Core i5-8500 CPU 3.00GHz (Coffee Lake), 1 CPU, 6 logical and 6 physical cores
Frequency=2929684 Hz, Resolution=341.3337 ns, Timer=TSC
  [Host] : .NET Framework 4.7.2 (CLR 4.0.30319.42000), 64bit RyuJIT-v4.7.3416.0
  Clr    : .NET Framework 4.7.2 (CLR 4.0.30319.42000), 64bit RyuJIT-v4.7.3416.0

Job=Clr  Runtime=Clr  

```
| Method |     Mean |     Error |    StdDev |   Median | Gen 0/1k Op | Gen 1/1k Op | Gen 2/1k Op | Allocated Memory/Op |
|------- |---------:|----------:|----------:|---------:|------------:|------------:|------------:|--------------------:|
|   List | 5.237 ns | 0.0138 ns | 0.0129 ns | 5.233 ns |      0.0085 |           - |           - |                40 B |
|  Array | 2.085 ns | 0.0033 ns | 0.0031 ns | 2.086 ns |      0.0051 |           - |           - |                24 B |
|   Linq | 2.053 ns | 0.0053 ns | 0.0050 ns | 2.052 ns |           - |           - |           - |                   - |
