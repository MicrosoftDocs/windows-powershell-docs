---
ms.technology: powershell-mdop
ms.mktglfcycl: manage
ms.author: kenwith
ms.prod: w10
ms.sitesec: library
author: kenwith
description: Use this topic to help manage MDOP technologies with Windows PowerShell.
external help file: Microsoft.AppV.AppVClientPowerShell.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro 
ms.assetid: B3A87671-64BD-4332-AAB8-FE9BDC6AE81D
ms.date: 2016-12-05
ms.devlang: powershell
ms.topic: reference
online version: 
schema: 2.0.0
title: Add-AppvClientConnectionGroup
---

# Add-AppvClientConnectionGroup

## SYNOPSIS
Creates a composition of multiple packages on a computer running the App-V client.

## SYNTAX

```
Add-AppvClientConnectionGroup [-Path] <String> [<CommonParameters>]
```

## DESCRIPTION
The **Add-AppvClientConnectionGroup** cmdlet creates an Microsoft Application Virtualization (App-V) connection group.
In order for the group to be applied, all packages in the group must be added to the target computer, and must not be running.

This cmdlet can also be used to update an already existing connection group definition.

## EXAMPLES

### Example 1: Add a connection group
```
PS C:\> Add-AppvClientConnectionGroup -Path "C:\MyApps\MyGroup.xml"
```

This command adds the connection group file to the computer from the path provided.

## PARAMETERS

### -Path
Specifies the App-V connection group definition file.

```yaml
Type: String
Parameter Sets: (All)
Aliases: PSPath

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.AppvAgent.AppvClientConnectionGroup

## NOTES

## RELATED LINKS

[Disable-AppvClientConnectionGroup](./Disable-AppvClientConnectionGroup.md)

[Enable-AppvClientConnectionGroup](./Enable-AppvClientConnectionGroup.md)

[Get-AppvClientConnectionGroup](./Get-AppvClientConnectionGroup.md)

[Mount-AppvClientConnectionGroup](./Mount-AppvClientConnectionGroup.md)

[Remove-AppvClientConnectionGroup](./Remove-AppvClientConnectionGroup.md)

[Repair-AppvClientConnectionGroup](./Repair-AppvClientConnectionGroup.md)

[Stop-AppvClientConnectionGroup](./Stop-AppvClientConnectionGroup.md)


