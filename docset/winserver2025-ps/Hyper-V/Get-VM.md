---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.HyperV.PowerShell.Cmdlets.dll-Help.xml
Module Name: Hyper-V
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hyper-v/get-vm?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-VM
---

# Get-VM

## SYNOPSIS
Gets the virtual machines from one or more Hyper-V hosts.

## SYNTAX

### Name (Default)
```
Get-VM [[-Name] <String[]>] [-CimSession <CimSession[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential[]>] [<CommonParameters>]
```

### Id
```
Get-VM [-CimSession <CimSession[]>] [-ComputerName <String[]>] [-Credential <PSCredential[]>] [[-Id] <Guid>]
 [<CommonParameters>]
```

### ClusterObject
```
Get-VM [-ClusterObject] <PSObject> [<CommonParameters>]
```

## DESCRIPTION
The **Get-VM** cmdlet gets the virtual machines from one or more Hyper-V hosts.

## EXAMPLES

### Example 1
```
PS C:\> Get-VM
```

This example gets all virtual machines on the local virtual machine host.

### Example 2
```
PS C:\> Get-VM -ComputerName Server1 | Where-Object {$_.State -eq 'Running'}
```

This example gets all virtual machines on Hyper-V host Server1 that are running.

### Example 3
```
PS C:\> Get-ClusterGroup | ? {$_.GroupType -eq 'VirtualMachine' } | Get-VM
```

This example gets all virtual machines in the cluster to which the local Hyper-V host is joined.

## PARAMETERS

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: Name, Id
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ClusterObject
Specifies the cluster resource or cluster group of the virtual machine to be retrieved.

```yaml
Type: PSObject
Parameter Sets: ClusterObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ComputerName
Specifies one or more Hyper-V hosts from which virtual machines are to be retrieved.
NetBIOS names, IP addresses, and fully qualified domain names are allowable.
The default is the local computer.
Use localhost or a dot (.) to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: Name, Id
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Credential
Specifies one or more user accounts that have permission to perform this action.
The default is the current user.

```yaml
Type: PSCredential[]
Parameter Sets: Name, Id
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Id
Specifies the identifier of the virtual machine to be retrieved.

```yaml
Type: Guid
Parameter Sets: Id
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Name
Specifies the name of the virtual machine to be retrieved.

```yaml
Type: String[]
Parameter Sets: Name
Aliases: VMName

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: True
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.HyperV.PowerShell.VirtualMachine

## NOTES

## RELATED LINKS

