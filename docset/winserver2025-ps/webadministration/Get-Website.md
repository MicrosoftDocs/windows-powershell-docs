---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
Module Name: WebAdministration
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/webadministration/get-website?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Website
---

# Get-Website

## SYNOPSIS
Gets configuration information for an IIS website.

## SYNTAX

```
Get-Website [[-Name] <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-Website** cmdlet gets configuration information for an Internet Information Services (IIS) website.

## EXAMPLES

### Example 1: Get information about the default website
```
IIS:\> Get-Website -Name "Default Web Site"
Name             ID State   Physical Path                 Bindings
----             -- -----   -------------                 --------
Default Web Site 1  Started %SystemDrive%\inetpub\wwwroot http *:80:
                                                          net.tcp 808:*
```

This command returns the configuration information for the default website.

## PARAMETERS

### -Name
Specifies the name of the website about which this cmdlet returns configuration information.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[New-Website](./New-Website.md)

[Remove-Website](./Remove-Website.md)

[Start-Website](./Start-Website.md)

[Stop-Website](./Stop-Website.md)

