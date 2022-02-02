# SimpleMath Projection Sample with Windows App SDK

This repo uses C#/WinRT to generate a projection from a simple C++/WinRT component, distribute the projection as a NuGet package, and consume the package from a Windows App SDK app.

Before building, make sure to go to **Build** -> **Configuration Manager**, and set all projects to x64. Note that the projection library project sets `<PlatformTarget>AnyCPU</PlatformTarget>` in order to build a non architecture-specific interop assembly, so that any consuming apps can reference the projection.

Build steps: 

1. Build **SimpleMathComponent** for all architectures: x64, x86, and ARM64.
2. Build **WinAppSDKSimpleMathProjection** to generate the NuGet package (the nuspec requires setting the platform to x64, but note that the output projection assembly is AnyCPU).
3. Restore the **SimpleMathComponent** package in **WinAppSDKApp** before building and running the app.
