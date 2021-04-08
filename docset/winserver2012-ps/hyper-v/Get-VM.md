---
author: Kateyanne
external help file: Hyper-V_Cmdlets.xml
Module Name: Hyper-V
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/hyper-v/get-vm?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-VM

## SYNOPSIS
Gets the virtual machines from one or more Hyper-V hosts.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-VM [[-Name] <String[]>] [-ComputerName <String[]>]
```

### UNNAMED_PARAMETER_SET_2
```
Get-VM [-ClusterObject] <PSObject>
```

### UNNAMED_PARAMETER_SET_3
```
Get-VM [[-Id] <Guid>] [-ComputerName <String[]>]
```

## DESCRIPTION
The **Get-VM** cmdlet gets the virtual machines from one or more Hyper-V hosts.

## EXAMPLES

### Example 1
```
PS C:\>Get-VM
```

This example gets all virtual machines on the local virtual machine host.

### Example 2
```
PS C:\>Get-VM -ComputerName Server1 | Where-Object {$_.State -eq 'Running'}
```

This example gets all virtual machines on Hyper-V host Server1 that are running.

### Example 3
```
PS C:\>Get-ClusterGroup | ? {$_.GroupType -eq 'VirtualMachine' } | Get-VM
```

This example gets all virtual machines in the cluster to which the local Hyper-V host is joined.

## PARAMETERS

### -ClusterObject
Specifies the cluster resource or cluster group of the virtual machine to be retrieved.

```yaml
Type: PSObject
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ComputerName
Specifies one or more Hyper-V hosts from which virtual machines are to be retrieved.
NetBIOS names, IP addresses, and fully-qualified domain names are allowable.
The default is the local computer - use "localhost" or a dot (".") to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_3
Aliases: 

Required: False
Position: Named
Default value: .
Accept pipeline input: False
Accept wildcard characters: False
```

### -Id
Specifies the identifier of the virtual machine to be retrieved.

```yaml
Type: Guid
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Name
Specifies the name of the virtual machine to be retrieved.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: True
```

## INPUTS

## OUTPUTS

### Microsoft.Virtualization.Powershell.VirtualMachine

## NOTES

## RELATED LINKS



