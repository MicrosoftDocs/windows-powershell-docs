---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
Module Name: WebAdministration
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/webadministration/get-webfilepath?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WebFilePath
---

# Get-WebFilePath

## SYNOPSIS
Gets the physical path to the location of the specified IIS module.

## SYNTAX

```
Get-WebFilePath [[-PSPath] <String[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-WebFilePath** cmdlet gets the physical path to the location of the specified Internet Information Services (IIS) module.

## EXAMPLES

### Example 1: Get the physical path of the default website
```
IIS:\> Get-WebFilePath -PSPath "IIS:\Sites\Default Web Site"
Directory: Microsoft.PowerShell.Core\FileSystem::C:\inetpub

Mode    LastWriteTime        Length    Name
----    -------------        ------    ----
d----   7/28/2008 9:40 PM              wwwroot
```

This command retrieves the physical path for the default website.

## PARAMETERS

### -PSPath
Specifies an IIS configuration path.

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

