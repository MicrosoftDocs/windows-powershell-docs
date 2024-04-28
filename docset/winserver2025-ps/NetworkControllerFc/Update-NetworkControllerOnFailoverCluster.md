---
external help file: NetworkControllerFc-help.xml
Module Name: NetworkControllerFc
ms.date: 02/21/2024
online version: https://learn.microsoft.com/powershell/module/networkcontrollerfc/update-networkcontrolleronfailovercluster?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Update-NetworkControllerOnFailoverCluster
---

# Update-NetworkControllerOnFailoverCluster

## SYNOPSIS
Upgrades the NetworkController to a New Version.

## SYNTAX

```
Update-NetworkControllerOnFailoverCluster [-UpgradePackagePath] <String> [<CommonParameters>]
```

## DESCRIPTION

Upgrades the NetworkController to a New Version.

- If the Application Version is unchanged this returns without changing any state.
- If the Application Version is higher, all services which have a higher service versions are
  upgraded.

## EXAMPLES

### Example 1

```powershell
PS C:\> {{ Add example code here }}
```

{{ Add example description here }}

## PARAMETERS

### -UpgradePackagePath

{{ Fill UpgradePackagePath Description }}

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS
