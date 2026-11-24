---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
Module Name: WebAdministration
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/webadministration/new-webapppool?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-WebAppPool
---

# New-WebAppPool

## SYNOPSIS
Creates an IIS application pool.

## SYNTAX

```
New-WebAppPool [-Name] <String> [-Force] [<CommonParameters>]
```

## DESCRIPTION
The **New-WebAppPool** cmdlet creates an Internet Information Services (IIS) application pool. For changing different properties of the application pool after creation, see [PowerShell Snap-in: Making Configuration Changes to Websites and App Pools](/iis/manage/powershell/powershell-snap-in-making-simple-configuration-changes-to-web-sites-and-application-pools).

## EXAMPLES

### Example 1: Create an IIS application pool
```powershell
IIS:\> New-WebAppPool -Name "NewAppPool"
```

This command creates an IIS application pool named NewAppPool.

### Example 2: Create an IIS application pool and set autoStart
```powershell
IIS:\> $newAppPool = New-WebAppPool -Name "NewAppPool"
IIS:\> $newAppPool.autoStart = "false"
IIS:\> $newAppPool | Set-Item
```

This command creates an IIS application pool named NewAppPool and sets **autoStart** property to false.

### Example 3: Create an IIS application pool and set managedRuntimeVersion
```powershell
IIS:\> New-WebAppPool -Name "NewAppPool"
IIS:\> Set-ItemProperty -Path IIS:\AppPools\NewAppPool managedRuntimeVersion "v4.0"
```

This command creates an IIS application pool named NewAppPool and sets **managedRuntimeVersion** property to v4.0.

## PARAMETERS

### -Force
Forces the command to run without asking for user confirmation.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of the IIS application pool to create.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Remove-WebAppPool](./Remove-WebAppPool.md)

[Restart-WebAppPool](./Restart-WebAppPool.md)

[Start-WebAppPool](./Start-WebAppPool.md)

[Stop-WebAppPool](./Stop-WebAppPool.md)
