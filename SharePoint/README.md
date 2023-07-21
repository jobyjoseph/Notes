Check if sharepoint is enabled
```sh
Get-Module -Name Microsoft.Online.SharePoint.PowerShell -ListAvailable | Select Name,Version
```

To install SharePoint module in powershell:
```sh
Install-Module -Name Microsoft.Online.SharePoint.PowerShell
```

To connect to a sharepoint site. Did not work with Powershell in mac:
```sh
Connect-SPOService -Url https://litmus7systemscons.sharepoint.com
```

Design template values:
68 - Communication site
64 - Team site
