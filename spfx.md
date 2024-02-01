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

### Create a site collection app catalog

Before running the following script, connect to your SharePoint Online tenant using the `Connect-SPOService` or the PnP version `Connect-PnPOnline`.

```
Add-SPOSiteCollectionAppCatalog -Site https://contoso.sharepoint.com/sites/marketing

or

Add-PnPSiteCollectionAppCatalog -site https://contoso.sharepoint.com/sites/marketing
```

Reference [Create site collection app catalog](https://learn.microsoft.com/en-us/sharepoint/dev/general-development/site-collection-app-catalog?WT.mc_id=M365-MVP-4030574#create-a-site-collection-app-catalog)

### Learn more about SPFx development:

- [SharePoint Framework Overview](https://aka.ms/spfx)
- [Use Microsoft Graph in your solution](https://aka.ms/spfx-yeoman-graph)
- [Build for Microsoft Teams using SharePoint Framework](https://aka.ms/spfx-yeoman-teams)
- [Build for Microsoft Viva Connections using SharePoint Framework](https://aka.ms/spfx-yeoman-viva)
- [Publish SharePoint Framework applications to the marketplace](https://aka.ms/spfx-yeoman-store)
- [SharePoint Framework API reference](https://aka.ms/spfx-yeoman-api)
- [Microsoft 365 Developer Community](https://aka.ms/m365pnp)
