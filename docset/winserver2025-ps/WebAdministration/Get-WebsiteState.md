---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
Module Name: WebAdministration
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/webadministration/get-websitestate?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WebsiteState
---

# Get-WebsiteState

## SYNOPSIS
Gets the state of an IIS website.

## SYNTAX

```
Get-WebsiteState [[-Name] <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-WebsiteState** cmdlet gets the state of an Internet Information Services (IIS) website.

## EXAMPLES

### Example 1: Get the state of a website
```
IIS:\> Get-WebsiteState -Name "Default Web Site"
Value
-----
Started
```

This command returns the state of the default website.

## PARAMETERS

### -Name
Specifies the name of the website about which this cmdlet gets information.

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

