# LensIsland.GameLibs

`LensIsland.GameLibs` is a package that provides stripped and publicized assemblies from the game [Len's Island], published to my GitHub NuGet feed.

_**This repository contains no actual code** — it exists entirely to provide a README for the corresponding NuGet package._

The goal is to provide IntelliSense, type inspection and the capability to build in CI environments without having to wire up DLLs for each project.

# How to use

## 1. Create Personal Access Token

Go to https://github.com/settings/tokens and create a Classic token with the following scope:
- ✅ `read:packages`
  
No other permissions are needed.

## 2. Add Package Registry as NuGet Source

Next, you must add the GitHub Package Registry as a NuGet source.

```
dotnet nuget add source \
  --username <your-github-username> \
  --password <your-personal-access-token> \
  --store-password-in-clear-text \
  --name github-csh \
  "https://nuget.pkg.github.com/csh/index.json"
```

Replace placeholders appropriately.

## 3. Add `LensIsland.GameLibs` as a Dependency

You should now be able to add the NuGet package as a dependency in your project, either by running the following command:

```
dotnet add package LensIsland.GameLibs
```
or via editing your `.csproj` to add a `PackageReference`
```
<PackageReference Include="LensIsland.GameLibs" Version="*" />
```

If I didn't screw up, this should give full IntelliSense support in your editor and make future project setup a breeze. :)

[Len's Island]: https://store.steampowered.com/app/1335830/Lens_Island/
