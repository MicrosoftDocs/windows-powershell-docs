---
external help file: Microsoft.HCS.Management.dll-Help.xml
Module Name: HCS
ms.date: 12/05/2017
online version: https://docs.microsoft.com/powershell/module/hcs/get-hcswuaversion?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-HcsWuaVersion
---

# Get-HcsWuaVersion

## SYNOPSIS
Gets the version of the Windows Update Agent.

## SYNTAX

```
Get-HcsWuaVersion [<CommonParameters>]
```

## DESCRIPTION
The **Get-HcsWuaVersion** cmdlet gets the version of the Windows Update Agent for StorSimple controllers.

## EXAMPLES

### Example 1: Get the version of the Windows Update Agent
```
PS C:\>Get-HcsWuaVersion
```

This command gets the version of the Windows Update Agent.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.HCS.Management.Patching.HcsWuaVersion
The HcsWuaVersion object has the following properties:

- string Controller 0 Version 
- string Controller 1 Version

## NOTES

## RELATED LINKS

[Get-HcsUpdateAvailability](./Get-HcsUpdateAvailability.md)

[Get-HcsUpdateStatus](./Get-HcsUpdateStatus.md)

[Start-HcsUpdate](./Start-HcsUpdate.md)

