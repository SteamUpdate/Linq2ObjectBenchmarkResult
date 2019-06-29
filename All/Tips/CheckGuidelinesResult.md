# ELMA2221

## Code
```csharp
[Benchmark(Description = "Array.Find with lambda")]
public Customer Test()
{
    return Array.Find(customers, delegate(Customer customer)
    {
        return customer.Name == "456";
    });
}

[Benchmark(Description = "Array.Find")]
public Customer Test1()
{
    return Array.Find(customers, customer => customer.Name == "456");
}

[Benchmark(Description = "FirstOrDefault")]
public Customer Test2()
{
    return customers.FirstOrDefault(customer => customer.Name == "456");
}
```

## Framework
|                   Method |    N |        Mean |      Error |     StdDev |      Median |  Gen 0 | Gen 1 | Gen 2 | Allocated |
|------------------------- |----- |------------:|-----------:|-----------:|------------:|-------:|------:|------:|----------:|
|   Array.Find with lambda |   10 |    29.39 ns |  0.2053 ns |  0.1921 ns |    29.52 ns |      - |     - |     - |         - |
|               Array.Find |   10 |    29.68 ns |  0.0991 ns |  0.0927 ns |    29.70 ns |      - |     - |     - |         - |
|           FirstOrDefault |   10 |   105.90 ns |  0.6391 ns |  0.5665 ns |   105.99 ns | 0.0067 |     - |     - |      32 B |
|   **Array.Find with lambda** |  **100** |   **289.26 ns** |  **1.4198 ns** |  **1.3281 ns** |   **289.53 ns** |      **-** |     **-** |     **-** |         **-** |
|               **Array.Find** |  **100** |   **288.63 ns** |  **3.2012 ns** |  **2.9944 ns** |   **289.44 ns** |      **-** |     **-** |     **-** |         **-** |
|           **FirstOrDefault** |  **100** |   **832.70 ns** |  **7.8619 ns** |  **7.3541 ns** |   **830.01 ns** | **0.0067** |     **-** |     **-** |      **32 B** |
|   Array.Find with lambda | 1000 | 1,876.29 ns | 23.7193 ns | 22.1870 ns | 1,886.82 ns |      - |     - |     - |         - |
|               Array.Find | 1000 | 1,870.03 ns | 11.9076 ns | 11.1384 ns | 1,867.84 ns |      - |     - |     - |         - |
|           FirstOrDefault | 1000 | 4,336.63 ns | 59.6608 ns | 55.8068 ns | 4,346.49 ns |      - |     - |     - |      32 B |

## Core
|                   Method |    N |        Mean |     Error |    StdDev |      Median |  Gen 0 | Gen 1 | Gen 2 | Allocated |
|------------------------- |----- |------------:|----------:|----------:|------------:|-------:|------:|------:|----------:|
|   Array.Find with lambda |   10 |    27.56 ns | 0.1215 ns | 0.1136 ns |    27.55 ns |      - |     - |     - |         - |
|               Array.Find |   10 |    27.58 ns | 0.1255 ns | 0.1174 ns |    27.53 ns |      - |     - |     - |         - |
|           FirstOrDefault |   10 |   119.15 ns | 0.1853 ns | 0.1734 ns |   119.09 ns | 0.0067 |     - |     - |      32 B |
|   **Array.Find with lambda** |  **100** |   **260.74 ns** | **0.6923 ns** | **0.5781 ns** |   **260.89 ns** |      **-** |     **-** |     **-** |         **-** |
|               **Array.Find** |  **100** |   **264.78 ns** | **4.3699 ns** | **4.0876 ns** |   **265.43 ns** |      **-** |     **-** |     **-** |         **-** |
|           **FirstOrDefault** |  **100** |   **818.95 ns** | **0.9944 ns** | **0.9301 ns** |   **818.74 ns** | **0.0067** |     **-** |     **-** |      **32 B** |
|   Array.Find with lambda | 1000 | 2,515.58 ns | 2.5403 ns | 2.3762 ns | 2,515.20 ns |      - |     - |     - |         - |
|               Array.Find | 1000 | 2,518.36 ns | 3.5953 ns | 3.3630 ns | 2,518.64 ns |      - |     - |     - |         - |
|           FirstOrDefault | 1000 | 4,645.33 ns | 6.3005 ns | 5.5852 ns | 4,645.14 ns |      - |     - |     - |      32 B |