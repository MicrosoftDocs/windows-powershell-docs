---
description: Removes the requested net intent.
external help file: NetworkAtc-help.xml
Module Name: NetworkATC
ms.date: 10/21/2021
online version: https://docs.microsoft.com/powershell/module/netwnv/remove-netintent?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-NetIntent
---

# Remove-NetIntent

## SYNOPSIS
Removes the requested net intent.

## SYNTAX

### ComputerName (Default)
```
Remove-NetIntent [-Name] <String> [[-ComputerName] <String>] [-SkipServiceStop <Boolean>] [<CommonParameters>]
```

### Cluster
```
Remove-NetIntent [-Name] <String> [-ClusterName] <String> [-SkipServiceStop <Boolean>] [<CommonParameters>]
```

## DESCRIPTION
This command removes the given NetIntent.
Note: (cluster) If the a ClusterName is specified, then the removal would impact all the nodes on the gievn cluster.
      (standalone) Only net intents for a given node will be removed

Remove-NetIntent 'does not'  remove the provisioning on the target hosts.
The device administrator should remove any old intent configuration from the node manually.

## EXAMPLES

### Example 1
```powershell
PS C:\> {{ Add example code here }}
```

{{ Add example description here }}

## PARAMETERS

### -ClusterName
{{ Fill ClusterName Description }}

```yaml
Type: String
Parameter Sets: Cluster
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName
{{ Fill ComputerName Description }}

```yaml
Type: String
Parameter Sets: ComputerName
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
{{ Fill Name Description }}

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SkipServiceStop
{{ Fill SkipServiceStop Description }}

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: True
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS
