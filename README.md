# BINDINGSGENERATOR error:

Minimal reproduction of a NRE in the Android bindings generator:

```
BINDINGSGENERATOR : error BG0000: System.NullReferenceException: Object reference not set to an instance of an object.
```

```
dotnet --version
8.0.100-rtm.23470.21
```

Stack trace from verbose output:
```
C:\Program Files\dotnet\packs\Microsoft.Android.Sdk.Windows\33.0.68\tools\Xamarin.Android.Bindings.Core.targets(79,5): message BG0000: error BG0000: System.NullReferenceException: Object reference not set to an instance of an object. [C:\src\aaaRepros\AndroidBindingNRE\AndroidBindingNRE.csproj]
    at MonoDroid.Generation.Parameter.get_Type() in /Users/runner/work/1/s/xamarin-android/external/Java.Interop/tools/generator/Java.Interop.Tools.Generator.ObjectModel/Parameter.cs:line 233
C:\Program Files\dotnet\packs\Microsoft.Android.Sdk.Windows\33.0.68\tools\Xamarin.Android.Bindings.Core.targets(79,5): message BG0000:    at MonoDroid.Generation.Parameter.get_Type() in /Users/runner/work/1/s/xamarin-android/external/Java.Interop/tools/generator/Java.Interop.Tools.Generator.ObjectModel/Parameter.cs:line 233 [C:\src\aaaRepros\AndroidBindingNRE\AndroidBindingNRE.csproj]
    at MonoDroid.Generation.MethodBase.<>c.<AutoDetectEnumifiedOverrideParameters>b__63_0(Parameter p) in /Users/runner/work/1/s/xamarin-android/external/Java.Interop/tools/generator/Java.Interop.Tools.Generator.ObjectModel/MethodBase.cs:line 37
C:\Program Files\dotnet\packs\Microsoft.Android.Sdk.Windows\33.0.68\tools\Xamarin.Android.Bindings.Core.targets(79,5): message BG0000:    at MonoDroid.Generation.MethodBase.<>c.<AutoDetectEnumifiedOverrideParameters>b__63_0(Parameter p) in /Users/runner/work/1/s/xamarin-android/external/Java.Interop/tools/generator/Java.Interop.Tools.Generator.ObjectModel/MethodBase.cs:line 37 [C:\src\aaaRepros\AndroidBindingNRE\AndroidBindingNRE.csproj]
    at System.Linq.Enumerable.All[TSource](IEnumerable`1 source, Func`2 predicate)
C:\Program Files\dotnet\packs\Microsoft.Android.Sdk.Windows\33.0.68\tools\Xamarin.Android.Bindings.Core.targets(79,5): message BG0000:    at System.Linq.Enumerable.All[TSource](IEnumerable`1 source, Func`2 predicate) [C:\src\aaaRepros\AndroidBindingNRE\AndroidBindingNRE.csproj]
    at MonoDroid.Generation.MethodBase.AutoDetectEnumifiedOverrideParameters(AncestorDescendantCache cache) in /Users/runner/work/1/s/xamarin-android/external/Java.Interop/tools/generator/Java.Interop.Tools.Generator.ObjectModel/MethodBase.cs:line 37
C:\Program Files\dotnet\packs\Microsoft.Android.Sdk.Windows\33.0.68\tools\Xamarin.Android.Bindings.Core.targets(79,5): message BG0000:    at MonoDroid.Generation.MethodBase.AutoDetectEnumifiedOverrideParameters(AncestorDescendantCache cache) in /Users/runner/work/1/s/xamarin-android/external/Java.Interop/tools/generator/Java.Interop.Tools.Generator.ObjectModel/MethodBase.cs:line 37 [C:\src\aaaRepros\AndroidBindingNRE\AndroidBindingNRE.csproj]
    at MonoDroid.Generation.GenBase.UpdateEnums(CodeGenerationOptions opt, AncestorDescendantCache cache) in /Users/runner/work/1/s/xamarin-android/external/Java.Interop/tools/generator/Java.Interop.Tools.Generator.ObjectModel/GenBase.cs:line 869
C:\Program Files\dotnet\packs\Microsoft.Android.Sdk.Windows\33.0.68\tools\Xamarin.Android.Bindings.Core.targets(79,5): message BG0000:    at MonoDroid.Generation.GenBase.UpdateEnums(CodeGenerationOptions opt, AncestorDescendantCache cache) in /Users/runner/work/1/s/xamarin-android/external/Java.Interop/tools/generator/Java.Interop.Tools.Generator.ObjectModel/GenBase.cs:line 869 [C:\src\aaaRepros\AndroidBindingNRE\AndroidBindingNRE.csproj]
    at MonoDroid.Generation.GenBase.UpdateEnums(CodeGenerationOptions opt, AncestorDescendantCache cache) in /Users/runner/work/1/s/xamarin-android/external/Java.Interop/tools/generator/Java.Interop.Tools.Generator.ObjectModel/GenBase.cs:line 867
C:\Program Files\dotnet\packs\Microsoft.Android.Sdk.Windows\33.0.68\tools\Xamarin.Android.Bindings.Core.targets(79,5): message BG0000:    at MonoDroid.Generation.GenBase.UpdateEnums(CodeGenerationOptions opt, AncestorDescendantCache cache) in /Users/runner/work/1/s/xamarin-android/external/Java.Interop/tools/generator/Java.Interop.Tools.Generator.ObjectModel/GenBase.cs:line 867 [C:\src\aaaRepros\AndroidBindingNRE\AndroidBindingNRE.csproj]
    at MonoDroid.Generation.GenBase.UpdateEnums(CodeGenerationOptions opt, AncestorDescendantCache cache) in /Users/runner/work/1/s/xamarin-android/external/Java.Interop/tools/generator/Java.Interop.Tools.Generator.ObjectModel/GenBase.cs:line 867
C:\Program Files\dotnet\packs\Microsoft.Android.Sdk.Windows\33.0.68\tools\Xamarin.Android.Bindings.Core.targets(79,5): message BG0000:    at MonoDroid.Generation.GenBase.UpdateEnums(CodeGenerationOptions opt, AncestorDescendantCache cache) in /Users/runner/work/1/s/xamarin-android/external/Java.Interop/tools/generator/Java.Interop.Tools.Generator.ObjectModel/GenBase.cs:line 867 [C:\src\aaaRepros\AndroidBindingNRE\AndroidBindingNRE.csproj]
    at MonoDroid.Generation.GenBase.UpdateEnums(CodeGenerationOptions opt, AncestorDescendantCache cache) in /Users/runner/work/1/s/xamarin-android/external/Java.Interop/tools/generator/Java.Interop.Tools.Generator.ObjectModel/GenBase.cs:line 879
C:\Program Files\dotnet\packs\Microsoft.Android.Sdk.Windows\33.0.68\tools\Xamarin.Android.Bindings.Core.targets(79,5): message BG0000:    at MonoDroid.Generation.GenBase.UpdateEnums(CodeGenerationOptions opt, AncestorDescendantCache cache) in /Users/runner/work/1/s/xamarin-android/external/Java.Interop/tools/generator/Java.Interop.Tools.Generator.ObjectModel/GenBase.cs:line 879 [C:\src\aaaRepros\AndroidBindingNRE\AndroidBindingNRE.csproj]
    at Xamarin.Android.Binder.CodeGenerator.Run(CodeGeneratorOptions options, DirectoryAssemblyResolver resolver) in /Users/runner/work/1/s/xamarin-android/external/Java.Interop/tools/generator/CodeGenerator.cs:line 257
C:\Program Files\dotnet\packs\Microsoft.Android.Sdk.Windows\33.0.68\tools\Xamarin.Android.Bindings.Core.targets(79,5): message BG0000:    at Xamarin.Android.Binder.CodeGenerator.Run(CodeGeneratorOptions options, DirectoryAssemblyResolver resolver) in /Users/runner/work/1/s/xamarin-android/external/Java.Interop/tools/generator/CodeGenerator.cs:line 257 [C:\src\aaaRepros\AndroidBindingNRE\AndroidBindingNRE.csproj]
    at Xamarin.Android.Binder.CodeGenerator.Run(CodeGeneratorOptions options) in /Users/runner/work/1/s/xamarin-android/external/Java.Interop/tools/generator/CodeGenerator.cs:line 50
C:\Program Files\dotnet\packs\Microsoft.Android.Sdk.Windows\33.0.68\tools\Xamarin.Android.Bindings.Core.targets(79,5): message BG0000:    at Xamarin.Android.Binder.CodeGenerator.Run(CodeGeneratorOptions options) in /Users/runner/work/1/s/xamarin-android/external/Java.Interop/tools/generator/CodeGenerator.cs:line 50 [C:\src\aaaRepros\AndroidBindingNRE\AndroidBindingNRE.csproj]
    at Xamarin.Android.Binder.CodeGenerator.Main(String[] args) in /Users/runner/work/1/s/xamarin-android/external/Java.Interop/tools/generator/CodeGenerator.cs:line 33
C:\Program Files\dotnet\packs\Microsoft.Android.Sdk.Windows\33.0.68\tools\Xamarin.Android.Bindings.Core.targets(79,5): message BG0000:    at Xamarin.Android.Binder.CodeGenerator.Main(String[] args) in /Users/runner/work/1/s/xamarin-android/external/Java.Interop/tools/generator/CodeGenerator.cs:line 33 [C:\src\aaaRepros\AndroidBindingNRE\AndroidBindingNRE.csproj]
    The command exited with code 1.
```