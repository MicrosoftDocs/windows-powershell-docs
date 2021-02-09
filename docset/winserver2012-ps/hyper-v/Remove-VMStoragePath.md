---
external help file: Hyper-V_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Remove-VMStoragePath

## SYNOPSIS
Removes a path from a storage resource pool.

## SYNTAX

```
Remove-VMStoragePath [-Path] <String[]> [-ResourcePoolName] <String[]> [-ResourcePoolType] <VMResourcePoolType>
 [-ComputerName <String[]>] [-PassThru]
```

## DESCRIPTION
The **Remove-VMStoragePath** cmdlet removes a path from a storage resource pool.

## EXAMPLES

### Example 1
```
PS C:\>Remove-VMStoragePath -Path D:\Test -ResourcePoolName VHD1 -ResourcePoolType VHD
```

Removes path D:\Test from VHD resource pool VHD1.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts on which a path is to be removed from a resource pool.
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

### -PassThru
Specifies that a **System.String** is to be passed through to the pipeline representing the path to be removed from the resource pool.

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

### -Path
Specifies the path to be removed from the storage resource pool.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ResourcePoolName
Specifies the name of the resource pool from which the path is to be removed.

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
Specifies the type of the resource pool from which the path is to be removed.
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

### None
Default

### System.String
If **-PassThru** is specified.

## NOTES

## RELATED LINKS



