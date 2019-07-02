# Конфигурация

``` ini
BenchmarkDotNet=v0.11.5

OS=Windows 10.0.14393.3025 (1607/AnniversaryUpdate/Redstone1)
Intel Core i5-8500 CPU 3.00GHz (Coffee Lake), 1 CPU, 6 logical and 6 physical cores
Frequency=2929688 Hz, Resolution=341.3333 ns, Timer=TSC

[Host] : .NET Framework 4.7.2 (CLR 4.0.30319.42000), 64bit RyuJIT-v4.7.3416.0
Clr    : .NET Framework 4.7.2 (CLR 4.0.30319.42000), 64bit RyuJIT-v4.7.3416.0

.NET Core SDK=2.2.105
[Host] : .NET Core 2.2.3 (CoreCLR 4.6.27414.05, CoreFX 4.6.27414.05), 64bit RyuJIT
Core   : .NET Core 2.2.3 (CoreCLR 4.6.27414.05, CoreFX 4.6.27414.05), 64bit RyuJIT

===================================================================================

OS=macOS Mojave 10.14.3 (18D109) [Darwin 18.2.0]
Intel Core i7-7820HQ CPU 2.90GHz (Kaby Lake), 1 CPU, 8 logical and 4 physical cores
.NET Core SDK=2.1.401
[Host] : .NET Core 2.1.3 (CoreCLR 4.6.26725.06, CoreFX 4.6.26725.05), 64bit RyuJIT
Core : .NET Core 2.1.3 (CoreCLR 4.6.26725.06, CoreFX 4.6.26725.05), 64bit RyuJIT
```

# Легенда

- N         : Value of the 'N' parameter
- Mean      : Arithmetic mean of all measurements
- Error     : Half of 99.9% confidence interval
- StdDev    : Standard deviation of all measurements
- Median    : Value separating the higher half of all measurements (50th percentile)
- Min       : Minimum
- Max       : Maximum
- Gen 0     : GC Generation 0 collects per 1000 operations
- Gen 1     : GC Generation 1 collects per 1000 operations
- Gen 2     : GC Generation 2 collects per 1000 operations
- Allocated : Allocated memory per single operation (managed only, inclusive, 1KB = 1024B)
- 1 ns      : 1 Nanosecond (0.000000001 sec)