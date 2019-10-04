---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-anbarr
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.HyperV.PowerShell.Cmdlets.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Set-VMHostCluster
ms.reviewer:
ms.assetid: E7E684CD-016F-44A9-A72B-A8B478EF2896
---

# Set-VMHostCluster

## SYNOPSIS
Configures a virtual machine host cluster.

## SYNTAX

### ClusterName (Default)
```
Set-VMHostCluster [-ClusterName] <String[]> [[-Credential] <PSCredential[]>] [-SharedStoragePath <String>]
 [-Passthru] [<CommonParameters>]
```

### CimSession
```
Set-VMHostCluster [-CimSession] <CimSession[]> [-SharedStoragePath <String>] [-Passthru] [<CommonParameters>]
```

### InputObject
```
Set-VMHostCluster [-InputObject] <VMHostCluster[]> [-SharedStoragePath <String>] [-Passthru]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-VMHostCluster** cmdlet configures a virtual machine host cluster.

## EXAMPLES

### Example 1: Configure a virtual machine host cluster
```
PS C:\> Set-VMHostCluster -ClusterName "ContosoCluster" -SharedStoragePath "D:\ClusterStorage\cluster01"
```

This command configures the shared storage path for the cluster named ContosoCluster.

## PARAMETERS

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a [New-CimSession](http://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](http://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: CimSession
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ClusterName
Specifies an array of names of the virtual machine host clusters that this cmdlet configures.

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

### -InputObject
Specifies an array of virtual machine host clusters that this cmdlet configures.
To obtain a **VMHostCluster** object, use the **Get-VMHostCluster** cmdlet.

```yaml
Type: VMHostCluster[]
Parameter Sets: InputObject
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Passthru
Indicates that this cmdlet returns the **Microsoft.HyperV.PowerShell.VMHostCluster** object that it configures.

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

### -SharedStoragePath
Specifies the location of the shared storage for the virtual machine host cluster.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.HyperV.PowerShell.VMHostCluster
This cmdlet returns a **VMHostCluster** object, if you specify the **Passthru** parameter.

## NOTES

## RELATED LINKS

[Get-VMHostCluster](./Get-VMHostCluster.md)

