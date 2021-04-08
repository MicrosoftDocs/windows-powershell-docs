---
author: Kateyanne
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
manager: dansimp
Module Name: WebAdministration
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/webadministration/new-webapppool?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# New-WebAppPool

## SYNOPSIS
Creates a new IIS application pool.

## SYNTAX

```
New-WebAppPool [-Name] <String> [-Force] [<CommonParameters>]
```

## DESCRIPTION
The **New-WebAppPool** cmdlet creates an Internet Information Services (IIS) application pool. For changing different properties of the application pool after creation, see [PowerShell Snap-in: Making Configuration Changes to Websites and App Pools](https://docs.microsoft.com/iis/manage/powershell/powershell-snap-in-making-simple-configuration-changes-to-web-sites-and-application-pools).

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
Forces the operation without prompting

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
The name of the IIS application pool to create.

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
