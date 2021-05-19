# SimpleMath Projection Sample with Project Reunion

This repo uses C#/WinRT to generate a projection, distribute as a NuGet package and consume it using Project Reunion templates.

Before building, make sure to go to **Build** -> **Configuration Manager**, and set all projects to x86/Win32. (You can also choose another configuration, but need to change the Configuration settings as well as the nuspec paths.

Note: Package restore will fail on **ProjectReunionApp**, since we first need to generate the SimpleMathComponent.nupkg.

To build and run:

- First build the **SimpleMathComponent.Interop** project. This should first build **SimpleMathComponent** (generating SimpleMathComponent.winmd). Then it will build the projection interop project, generating SimpleMathComponent.Interop.dll as well as the SimpleMathComponent.nupkg.
- Then set **ProjectReunionApp (Package)** as the Startup Project, right-click on the Solution -> Restore NuGet Packages, and then you can build and deploy **ProjectReunionApp (Package)**.
