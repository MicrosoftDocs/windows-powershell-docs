---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.HyperV.PowerShell.Cmdlets.dll-Help.xml
Module Name: Hyper-V
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hyper-v/get-vmhostcluster?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-VMHostCluster
---

# Get-VMHostCluster

## SYNOPSIS
Gets virtual machine host clusters.

## SYNTAX

### ClusterName (Default)
```
Get-VMHostCluster [-ClusterName] <String[]> [[-Credential] <PSCredential[]>] [<CommonParameters>]
```

### CimSession
```
Get-VMHostCluster [-CimSession] <CimSession[]> [<CommonParameters>]
```

## DESCRIPTION
The **Get-VMHostCluster** cmdlet gets **VMHostCluster** objects.

## EXAMPLES

### Example 1: Get a virtual machine host cluster
```
PS C:\> Get-VMHostCluster -ClusterName "ContosoCluster"
```

This command gets the **VMHostCluster** object for the cluster named ContosoCluster.

## PARAMETERS

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: CimSession
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ClusterName
Specifies an array of names of the virtual machine host clusters that this cmdlet gets.

```yaml
Type: String[]
Parameter Sets: ClusterName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Credential
Specifies one or more user accounts that have permission to perform this action.
The default is the current user.

```yaml
Type: PSCredential[]
Parameter Sets: ClusterName
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.HyperV.PowerShell.VMHostCluster
This cmdlet returns a **VMHostCluster** object.

## NOTES

## RELATED LINKS

[Set-VMHostCluster](./Set-VMHostCluster.md)

