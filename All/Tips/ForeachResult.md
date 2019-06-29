# `foreach`

## Code
```csharp
public void Common()
{
    foreach (var item in list)
    {
        if (item.GetType().FullName == typeof(Entity).FullName)
        {

        }
    }
}

public void Optimized()
{
    var typeName = typeof(Entity).FullName;
    foreach (var item in list)
    {
        if (item.GetType().FullName == typeName)
        {

        }
    }
}
```

## Framework
|    Method |    N |        Mean |       Error |      StdDev |      Median | Gen 0 | Gen 1 | Gen 2 | Allocated |
|---------- |----- |------------:|------------:|------------:|------------:|------:|------:|------:|----------:|
|    Common |   10 |    683.3 ns |   0.1014 ns |   0.0847 ns |    683.3 ns |     - |     - |     - |         - |
| Optimized |   10 |    435.8 ns |   0.1084 ns |   0.1014 ns |    435.7 ns |     - |     - |     - |         - |
|    **Common** |  **100** |  **6,560.5 ns** |   **1.0682 ns** |   **0.9469 ns** |  **6,560.7 ns** |     **-** |     **-** |     **-** |         **-** |
| **Optimized** |  **100** |  **3,831.6 ns** |   **9.3091 ns** |   **8.2523 ns** |  **3,828.1 ns** |     **-** |     **-** |     **-** |         **-** |
|    Common | 1000 | 67,610.2 ns | 471.8502 ns | 441.3689 ns | 67,798.6 ns |     - |     - |     - |         - |
| Optimized | 1000 | 37,373.8 ns |  38.7014 ns |  36.2013 ns | 37,362.5 ns |     - |     - |     - |         - |

## Core
|    Method |    N |        Mean |       Error |     StdDev |      Median | Gen 0 | Gen 1 | Gen 2 | Allocated |
|---------- |----- |------------:|------------:|-----------:|------------:|------:|------:|------:|----------:|
|    Common |   10 |    620.2 ns |   0.4253 ns |  0.3770 ns |    620.3 ns |     - |     - |     - |         - |
| Optimized |   10 |    386.5 ns |   0.1853 ns |  0.1734 ns |    386.4 ns |     - |     - |     - |         - |
|    **Common** |  **100** |  **6,034.8 ns** |  **10.6413 ns** |  **9.9539 ns** |  **6,036.4 ns** |     **-** |     **-** |     **-** |         **-** |
| **Optimized** |  **100** |  **3,479.5 ns** |   **5.8151 ns** |  **5.1549 ns** |  **3,478.6 ns** |     **-** |     **-** |     **-** |         **-** |
|    Common | 1000 | 60,552.9 ns |  75.9662 ns | 71.0588 ns | 60,563.1 ns |     - |     - |     - |         - |
| Optimized | 1000 | 34,476.2 ns | 102.8888 ns | 96.2423 ns | 34,433.9 ns |     - |     - |     - |         - |
