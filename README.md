This is a small repo created solely to reproduce an error that happens with VS 17.12.3 (.NET 9.0.101) when building a project that uses Blazor.BrowserExtension.Template.

Here's the [link for the issue](https://github.com/dotnet/aspnetcore/issues/59625).

To reproduce the error, just try building the project. This is the resulting error:
```
The "DiscoverPrecompressedAssets" task failed unexpectedly.
System.InvalidOperationException: Fingerprint for '...\ExtensionTest\ExtensionTest\obj\Debug\net8.0\browserextension\build\BackgroundWorker.js' is not defined.
   at Microsoft.AspNetCore.StaticWebAssets.Tasks.StaticWebAsset.Validate()
   at Microsoft.AspNetCore.StaticWebAssets.Tasks.StaticWebAsset.FromTaskItem(ITaskItem item)
   at System.Linq.Enumerable.WhereSelectArrayIterator`2.MoveNext()
   at System.Linq.Buffer`1..ctor(IEnumerable`1 source)
   at System.Linq.Enumerable.ToArray[TSource](IEnumerable`1 source)
   at Microsoft.AspNetCore.StaticWebAssets.Tasks.DiscoverPrecompressedAssets.Execute()
   at Microsoft.Build.BackEnd.TaskExecutionHost.Execute()
   at Microsoft.Build.BackEnd.TaskBuilder.<ExecuteInstantiatedTask>d__26.MoveNext()
```
