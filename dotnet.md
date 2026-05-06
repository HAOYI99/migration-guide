# Dotnet Migration

## Migrate sln to slnx

using .net cli

1. Check SDK Version Ensure you have .NET SDK 9.0.200+:

```
dotnet --version
```

2. Run Migration Command From the folder containing your .sln file:

```
dotnet sln migrate
```

If multiple .sln files exist, specify one explicitly:

```
dotnet sln MyApp.sln migrate
```

3. Validate Build and test with:

```
dotnet build MyApp.slnx
dotnet test MyApp.slnx
```

4. Clean Up Once validated, remove the old .sln to avoid confusion:

```
rm MyApp.sln
```

Update CI/CD scripts to reference .slnx.

## .NET upgrade assistant

1. Install the .NET Upgrade Assistant tool globally if you haven't already:

```
dotnet tool install -g upgrade-assistant
```

2. Run the upgrade assistant on your solution:

```
upgrade-assistant upgrade MyApp.sln
```

## References

https://codewithmukesh.com/blog/slnx-solution-format-dotnet/
