# Test for .Net Core projects sharing assembly infos

Some of you may know the good old shared assembly infos for .Net Full-Framework solutions where you store your common assembly-info entries (version, copyright, etc.) in a shared file which you then link into all your assemblies to get them compiled into the binaries.

As we are in the process of moving on to .Net Core (or at least support it side-by-side with the Full-Framework) I did some research and testing how this can be achieved in the new .Net world.

**In short:** yes, it can be done but with the .Net Core versions also this system changed already.

This repo demonstrates how to do it with .Net Core 2.1 and the new/current XML-based .csproj projects powered by MSBuild 15 and Visual Studio 2017.

## Key points

1. Create a file called `Directory.Build.props` somewhere up in the folder hierarchy of your projects. For example in the repo root.
1. Fill this file your shared properties. See [mine...](Directory.Build.props)
1. Remove the shared properties from your .csproj files. Otherwise you get ugly error messages from VisualStudio and MSBuild reporting a "Error for importing ...".
1. Build your solution and check the binaries. Happy.

## Links with more information:

- [COMMON MSBUILD PROPERTIES AND ITEMS WITH DIRECTORY.BUILD.PROPS](https://www.thomaslevesque.com/2017/09/18/common-msbuild-properties-and-items-with-directory-build-props/)
- [MS Docs: Customize your build](https://docs.microsoft.com/en-us/visualstudio/msbuild/customize-your-build)