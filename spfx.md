# SharePoint Framework

### Run specific generator version

Note: yo must not be globally installed

```
npx -p yo -p @microsoft/generator-sharepoint@1.12.1 -- yo @microsoft/sharepoint --skip-install
```

or other options

```
--package-manager pnpm
```

### Remove an app

```
$name = '*somename*'
$app = Get-PnPApp -Scope Site | Where-Object {$_.Title -like $name}

Uninstall-PnPApp -Identity $app.id -Scope Site
Remove-PnPApp -Identity $app.id -Scope Site
```
