---
Module Name: HPC
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hpc/get-hpcnetworkinterface?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-HpcNetworkInterface
---

# Get-HpcNetworkInterface

## SYNOPSIS
Gets network interfaces on the head node.

## SYNTAX

### Type (Default)
```
Get-HpcNetworkInterface [[-Type] <String[]>] [-Scheduler <String[]>]
 [<CommonParameters>]
```

### Name
```
Get-HpcNetworkInterface [-Name <String[]>] [-Scheduler <String[]>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-HpcNetworkInterface** cmdlet gets the network interfaces on the head node that have one or more specified names or one or more specified types.
If you do not specify any names or types, the **Get-HpcNetworkInterface** cmdlet gets all of the network interfaces on the head node.

## EXAMPLES

### Example 1: Get all network interfaces
```
PS C:\>Get-HpcNetworkInterace
```

This command gets all of the network interfaces on the head node of the HPC cluster.

### Example 2: Get network interfaces by type
```
PS C:\>Get-HpcNetworkInterface -Type "Enterprise,Private"
```

This command gets all of the network interfaces on the head node that have a type of Enterprise or Private.

## PARAMETERS

### -Name
Specifies an array of names for the network interfaces that you want to get.
You cannot specify both the *Name* and *Type* parameters.

```yaml
Type: String[]
Parameter Sets: Name
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Scheduler
Specifies the host name or IP address of the head node for the cluster.
The value must be a valid computer name or IP address.
If you do not specify the *Scheduler* parameter, this cmdlet uses the scheduler on the head node that the CCP_SCHEDULER environment variable specifies.
To set this environment variable, run the following cmdlet:

`Set-Content Env:CCP_SCHEDULER \<head_node_name\>`

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Type
Specifies an array of types for the network interfaces that you want to get.
Valid types are:

- Enterprise
- Private
- Application

You cannot specify both the *Type* and *Name* parameters.

```yaml
Type: String[]
Parameter Sets: Type
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### HpcNetworkBinding[]

## NOTES
* You must be a cluster administrator to run this cmdlet successfully.

## RELATED LINKS

[Get-HpcNetworkTopology](./Get-HpcNetworkTopology.md)
