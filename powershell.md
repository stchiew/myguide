---
title: PowerShell
nav_order: 5
layout: home
---

# PowerShell

### Count items in folder

If you want to recursively count folders and/or files in your parent folder, add the Recurse parameter to the previous commands, as follows:

Recursively count all files and subfolders in a folder:

` (Get-ChildItem -Recurse | Measure-Object).Count`

Recursively count only subfolders in a directory:

`(Get-ChildItem -Recurse -Directory | Measure-Object).Count`

Recursively count only files in a folder:

`(Get-ChildItem -Recurse -File | Measure-Object).Count`

### Loaded Assemblies

Display loaded assemblies in grid view

```
 [System.AppDomain]::CurrentDomain.GetAssemblies() | Where-Object Location |
 Sort-Object -Property FullName |
 Select-Object -Property FullName, Location, GlobalAssemblyCache, IsFullyTrusted |
 Out-GridView
```

Various ways to filter and display loaded assemblies

```
$LoadedAssemblies = [System.AppDomain]::CurrentDomain.GetAssemblies() | Where-Object Location -like '*Az.Storage*'
$LoadedAssemblies | Select-Object Location

$LoadedAssemblies | Where-Object Location -like '*Microsoft.Indentity.*.dll' | Select-Object -ExpandProperty FullName
```
