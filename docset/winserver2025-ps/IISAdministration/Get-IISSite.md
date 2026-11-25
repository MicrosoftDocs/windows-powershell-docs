---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IIS.Powershell.Commands.dll-Help.xml
Module Name: IISAdministration
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/iisadministration/get-iissite?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-IISSite
---

# Get-IISSite

## SYNOPSIS
Gets configuration information for an IIS Web site.

## SYNTAX

```
Get-IISSite [[-Name] <String[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-IISSite** cmdlet gets information about Internet Information Services (IIS) web sites and their current status and other key information.
If you a request a specific site or a comma delimited list of sites, only those whose names are passed as an argument are returned.
Otherwise all the websites are returned.

## EXAMPLES

### Example 1: Get information about an IIS website
```
PS C:\> Get-IISSite "Default Web Site"
```

This command gets the configuration information for the Default Web Site.

### Example 2: Get information about all IIS websites
```
PS C:\> Get-IISSite
Name             ID   State      Physical Path                  Bindings
----             --   -----      -------------                  --------
Default Web Site 1    Started    %SystemDrive%\inetpub\wwwroot  http *:80:
PattiFul         2    Stopped    C:\inetpub\PattiFul            http *:8080:
                                                                http *:8033:
FTPSite          3               C:\inetpub\ftproot             ftp *:21:
DavidChe         4    Started    c:\                            http *:8088:
MyNewSite        6555 Started    C:\inetpub\wwwroot             http *:8099:
                                                                http *:8022:
```

This command gets all configuration information about all IIS websites

### Example 3: Get an attribute for an IIS website
```
PS C:\> $Site = Get-IISSite "Default Web Site"
PS C:\> $Site.Attributes["ServerAutoStart"]
IsInheritedFromDefaultValue : True
IsProtected                 : False
Name                        : serverAutoStart
Schema                      : Microsoft.Web.Administration.ConfigurationAttributeSchema
Value                       : True
```

This command gets the ServerAutoStart attribute for the IIS Default Web Site.

## PARAMETERS

### -Name
Specifies the name of the IIS website to get configuration information.
If this parameter is not used, all sites are returned.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String[]

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[New-IISSite](./New-IISSite.md)

[Remove-IISSite](./Remove-IISSite.md)

[Start-IISSite](./Start-IISSite.md)

[Stop-IISSite](./Stop-IISSite.md)

[IIS Administration Cmdlets for Windows PowerShell](./iisadministration.md)

