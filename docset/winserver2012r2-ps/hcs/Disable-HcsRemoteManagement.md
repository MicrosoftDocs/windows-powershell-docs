---
external help file: Microsoft.HCS.Management.dll-Help.xml
Module Name: HCS
ms.date: 12/05/2017
online version: https://learn.microsoft.com/powershell/module/hcs/disable-hcsremotemanagement?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-HcsRemoteManagement
---

# Disable-HcsRemoteManagement

## SYNOPSIS
Disables Windows PowerShell remote management.

## SYNTAX

```
Disable-HcsRemoteManagement [<CommonParameters>]
```

## DESCRIPTION
The **Disable-HcsRemoteManagement** cmdlet disables Windows PowerShell® remote management for a device.
This cmdlet disables remote access for the following configurations: 

- SSAdminConsole session configuration
- Support session configuration

You cannot disable the Windows PowerShell session configuration that StorSimple Snapshot Manager uses.

## EXAMPLES

### Example 1: Disable remote management
```
PS C:\> Disable-HcsRemoteManagement
```

This command disables remote management for your device.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

###  
This cmdlet does not generate any output.

## NOTES

## RELATED LINKS

[Enable-HcsRemoteManagement](./Enable-HcsRemoteManagement.md)

