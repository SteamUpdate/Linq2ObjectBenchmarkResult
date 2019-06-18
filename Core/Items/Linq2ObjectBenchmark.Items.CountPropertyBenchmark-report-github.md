``` ini

BenchmarkDotNet=v0.11.5, OS=Windows 10.0.14393.2999 (1607/AnniversaryUpdate/Redstone1)
Intel Core i5-8500 CPU 3.00GHz (Coffee Lake), 1 CPU, 6 logical and 6 physical cores
Frequency=2929684 Hz, Resolution=341.3337 ns, Timer=TSC
.NET Core SDK=2.2.105
  [Host] : .NET Core 2.2.3 (CoreCLR 4.6.27414.05, CoreFX 4.6.27414.05), 64bit RyuJIT
  Core   : .NET Core 2.2.3 (CoreCLR 4.6.27414.05, CoreFX 4.6.27414.05), 64bit RyuJIT

Job=Core  Runtime=Core  

```
|    Method |    N |      Mean |     Error |    StdDev |    Median |       Min |       Max | Rank | Gen 0 | Gen 1 | Gen 2 | Allocated |
|---------- |----- |----------:|----------:|----------:|----------:|----------:|----------:|-----:|------:|------:|------:|----------:|
|      **List** |   **10** | **0.0118 ns** | **0.0013 ns** | **0.0011 ns** | **0.0116 ns** | **0.0105 ns** | **0.0143 ns** |    **1** |     **-** |     **-** |     **-** |         **-** |
| HashedSet |   10 | 0.4978 ns | 0.0020 ns | 0.0018 ns | 0.4976 ns | 0.4949 ns | 0.5010 ns |    5 |     - |     - |     - |         - |
|     Array |   10 | 0.0174 ns | 0.0018 ns | 0.0016 ns | 0.0171 ns | 0.0156 ns | 0.0210 ns |    3 |     - |     - |     - |         - |
|      **List** |  **100** | **0.0201 ns** | **0.0022 ns** | **0.0019 ns** | **0.0200 ns** | **0.0167 ns** | **0.0236 ns** |    **4** |     **-** |     **-** |     **-** |         **-** |
| HashedSet |  100 | 0.4988 ns | 0.0041 ns | 0.0038 ns | 0.4991 ns | 0.4936 ns | 0.5064 ns |    5 |     - |     - |     - |         - |
|     Array |  100 | 0.0183 ns | 0.0013 ns | 0.0011 ns | 0.0183 ns | 0.0169 ns | 0.0206 ns |    3 |     - |     - |     - |         - |
|      **List** | **1000** | **0.0175 ns** | **0.0016 ns** | **0.0015 ns** | **0.0179 ns** | **0.0143 ns** | **0.0192 ns** |    **3** |     **-** |     **-** |     **-** |         **-** |
| HashedSet | 1000 | 0.5008 ns | 0.0031 ns | 0.0029 ns | 0.5002 ns | 0.4972 ns | 0.5071 ns |    5 |     - |     - |     - |         - |
|     Array | 1000 | 0.0156 ns | 0.0015 ns | 0.0014 ns | 0.0156 ns | 0.0133 ns | 0.0177 ns |    2 |     - |     - |     - |         - |
