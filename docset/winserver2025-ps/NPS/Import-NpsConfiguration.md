---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.NPS.Commands.dll-Help.xml
Module Name: NPS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/nps/import-npsconfiguration?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Import-NpsConfiguration
---

# Import-NpsConfiguration

## SYNOPSIS
Imports NPS settings.

## SYNTAX

```
Import-NpsConfiguration [-Path] <String> [<CommonParameters>]
```

## DESCRIPTION
The **Import-NpsConfiguration** cmdlet imports settings for Network Policy Server (NPS).
NPS manages network access policies, connection request authentication, and connection request authorization.
You can use NPS as a Remote Authentication Dial-In User Service (RADIUS) proxy to forward connection requests to NPS or other RADIUS servers that you configure in remote RADIUS server groups.
For more information about NPS, see [Network Policy Server](https://technet.microsoft.com/en-us/library/cc732912.aspx) on TechNet.

## EXAMPLES

### Example 1: Import settings to a Network Policy Server
```
PS C:\>Import-NpsConfiguration -Path "C:\Npsconfig.xml"
```

This command imports settings from the file named C:\Npsconfig.xml to NPS.

## PARAMETERS

### -Path
Specifies the full file path of the NPS configuration to import.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Export-NpsConfiguration](./Export-NpsConfiguration.md)

