---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
Module Name: WebAdministration
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/webadministration/get-webconfigurationlock?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WebConfigurationLock
---

# Get-WebConfigurationLock

## SYNOPSIS
Gets the lock status of an IIS configuration location.

## SYNTAX

```
Get-WebConfigurationLock [-Location <String[]>] [-Filter] <String[]> [[-PSPath] <String[]>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-WebConfigurationLock** cmdlet gets the locking status of the specified Internet Information Services (IIS) configuration location.

## EXAMPLES

### Example 1: Get the locking status of an IIS configuration
```
IIS:\> Get-WebConfigurationLock -Filter "//asp" -PSPath "IIS:\"
```

This command returns the locking status of the asp IIS configuration section.

## PARAMETERS

### -Filter
Specifies an XPath filter expression.
This expression can be in XPath format.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Location
Specifies the location of the IIS configuration setting.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PSPath
Specifies an IIS configuration path in the format computer name/webroot/apphost.

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

[Add-WebConfigurationLock](./Add-WebConfigurationLock.md)

[Remove-WebConfigurationLock](./Remove-WebConfigurationLock.md)

