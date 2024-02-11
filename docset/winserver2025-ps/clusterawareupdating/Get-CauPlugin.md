---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: ClusterAwareUpdating.dll-Help.xml
Module Name: ClusterAwareUpdating
ms.date: 09/27/2022
online version: https://learn.microsoft.com/powershell/module/clusterawareupdating/get-cauplugin?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-CauPlugin
---

# Get-CauPlugin

## SYNOPSIS
Gets information about one or more software updating plug-ins that are registered on the local
computer.

## SYNTAX

```
Get-CauPlugin [[-Name] <String>] [<CommonParameters>]
```

## DESCRIPTION

The `Get-CauPlugin` cmdlet gets information about one or more software updating plug-ins that are
registered on the local computer. A plug-in can be specified or information can be retrieved about
all registered plug-ins.

CAU always uses a plug-in when performing updates. The default is the
**Microsoft.WindowsUpdatePlugin** plug-in. This plug-in communicates with the Windows Update agent,
the same software that is used when updates are downloaded from Windows Update or Microsoft Update,
or from a Windows Server Update Services (WSUS) server. For more information about how plug-ins work
in CAU, see [How CAU Plug-ins Work](https://go.microsoft.com/fwlink/p/?LinkId=235333).

## EXAMPLES

### Example 1: Get information about software update plug-ins

```powershell
Get-CauPlugin | Format-List -Property "*"
```

This command gets information about the software updating plug-ins that are registered in the local
CAU tool.

## PARAMETERS

### -Name

Specifies the name of the plug-in whose information this cmdlet gets.
If not specified, then information for all the registered plug-ins is returned.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Microsoft.ClusterAwareUpdating.CauPlugin

## NOTES

## RELATED LINKS

[Register-CauPlugin](./Register-CauPlugin.md)

[Unregister-CauPlugin](./Unregister-CauPlugin.md)

