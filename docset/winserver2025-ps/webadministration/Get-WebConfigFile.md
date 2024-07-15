---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
Module Name: WebAdministration
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/webadministration/get-webconfigfile?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WebConfigFile
---

# Get-WebConfigFile

## SYNOPSIS
Gets the file system path of the web.config file.

## SYNTAX

```
Get-WebConfigFile [[-PSPath] <String[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-WebConfigFile** cmdlet gets the physical path of the Internet Information Services (IIS) configuration file at the specified IIS module namespace path.

## EXAMPLES

### Example 1: Open the Web.config file for the default website
```
IIS:\> Notepad (Get-WebConfigFile -PSPath "IIS:\Sites\Default Web Site")
```

This command uses Notepad to open the Web.config file for the default website.

## PARAMETERS

### -PSPath
Specifies the IIS module namespace path to the site that contains the Web.config file.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
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

