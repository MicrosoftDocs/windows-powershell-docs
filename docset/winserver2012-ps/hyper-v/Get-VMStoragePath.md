---
external help file: Hyper-V_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: kenwith
author: kenwith
---

# Get-VMStoragePath

## SYNOPSIS
Gets the storage paths in a storage resource pool.

## SYNTAX

```
Get-VMStoragePath [[-Path] <String[]>] [-ResourcePoolName] <String[]> [-ResourcePoolType] <VMResourcePoolType>
 [-ComputerName <String[]>]
```

## DESCRIPTION
The **Get-VMStoragePath** cmdlet gets the storage paths in a storage resource pool.

## EXAMPLES

### Example 1
```
PS C:\>Get-VMStoragePath -ResourcePoolName VHD1 -ResourcePoolType VHD
```

Gets the storage paths from virtual hard drive resource pool VHD1.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts on which storage paths are to be retrieved.
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

### -Path
Specifies the path for which matching storage paths are to be retrieved.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ResourcePoolName
Specifies the name of the resource pool for which storage paths are to be retrieved.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourcePoolType
Specifies the type of the resource pool for which storage paths are to be retrieved.
Allowed values are **VFD**, **ISO**, and **VHD**.

```yaml
Type: VMResourcePoolType
Parameter Sets: (All)
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

### System.String

## NOTES

## RELATED LINKS

[00000000-0000-0000-0000-000000000000](00000000-0000-0000-0000-000000000000)

