---
external help file: Hyper-V_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Get-VMResourcePool

## SYNOPSIS
Gets the resource pools on one or more virtual machine hosts.

## SYNTAX

```
Get-VMResourcePool [[-Name] <String[]>] [[-ResourcePoolType] <VMResourcePoolType[]>] [-ComputerName <String[]>]
```

## DESCRIPTION
The **Get-VMResourcePool** cmdlet gets the resource pools on one or more virtual machine hosts.

## EXAMPLES

### Example 1
```
PS C:\>Get-VMResourcePool * VHD
```

Get all VHD resource pools on the local virtual machine host.

### Example 2
```
PS C:\>Get-VMResourcePool Test*
```

Get all resource pools on the local virtual machine host having a name that starts with Test.

### Example 3
```
PS C:\>Get-VMResourcePoolTest "test resource pool" VHD
```

Get all VHD resource pools on the local virtual machine host named test resource pool.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts on which the resource pools are to be retrieved.
NetBIOS names, IP addresses, and fully-qualified domain names are allowable.
The default is the local computer - use "localhost" or a dot (".") to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: .
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of the resource pool or pools to be retrieved.
Wildcards are allowed.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: True
```

### -ResourcePoolType
Specifies the type of the resource pool or pools to be retrieved.

```yaml
Type: VMResourcePoolType[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

## INPUTS

## OUTPUTS

### Microsoft.Virtualization.Powershell.ResourcePool

## NOTES

## RELATED LINKS



