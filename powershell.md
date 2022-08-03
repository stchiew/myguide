# PowerShell

### Count items in folder

If you want to recursively count folders and/or files in your parent folder, add the Recurse parameter to the previous commands, as follows:

Recursively count all files and subfolders in a folder:

` (Get-ChildItem -Recurse | Measure-Object).Count`

Recursively count only subfolders in a directory:

`(Get-ChildItem -Recurse -Directory | Measure-Object).Count`

Recursively count only files in a folder:

`(Get-ChildItem -Recurse -File | Measure-Object).Count`
