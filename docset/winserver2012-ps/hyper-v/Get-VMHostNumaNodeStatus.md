---
external help file: Hyper-V_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: kenwith
author: kenwith
---

# Get-VMHostNumaNodeStatus

## SYNOPSIS
Gets the status of the virtual machines on the non-uniform memory access (NUMA) nodes of a virtual machine host or hosts.

## SYNTAX

```
Get-VMHostNumaNodeStatus [[-ComputerName] <String[]>] [-Id <Int32>]
```

## DESCRIPTION
Gets the status of the virtual machines on the non-uniform memory access (NUMA) nodes of a virtual machine host or hosts.
If the virtual machine host enables NUMA spanning, this cmdlet returns an error.

## EXAMPLES

### Example 1
```
PS C:\>Get-VMHostNumaNodeStatus
```

Gets the status of the virtual machines on the non-uniform memory access (NUMA) nodes of the local Hyper-V host.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts on which NUMA node status is to be retrieved.
NetBIOS names, IP addresses, and fully-qualified domain names are allowable.
The default is the local computer - use "localhost" or a dot (".") to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: .
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Id
Identifies a NUMA node for which virtual machine status is to be retrieved.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

### VMNumaNodeStatus[]

## NOTES

## RELATED LINKS

[00000000-0000-0000-0000-000000000000](00000000-0000-0000-0000-000000000000)

