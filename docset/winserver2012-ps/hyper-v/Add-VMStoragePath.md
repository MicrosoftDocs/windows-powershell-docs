---
external help file: Hyper-V_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-anbarr
author: andreabarr
---

# Add-VMStoragePath

## SYNOPSIS
Adds a path to a storage resource pool.

## SYNTAX

```
Add-VMStoragePath [-Path] <String[]> [-ResourcePoolName] <String[]> [-ResourcePoolType] <VMResourcePoolType>
 [-ComputerName <String[]>] [-PassThru]
```

## DESCRIPTION
The **Add-VMStoragePath** cmdlet adds a path to a storage resource pool.

## EXAMPLES

### Example 1
```
PS C:\>Add-VMStoragePath -Path D:\VHD -ResourcePoolName "Engineering Department" -ResourcePoolType VHD
```

Adds path D:\VHD to resource storage pool Engineering Department of type VHD.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts on which the path to the storage resource pool is to be added.
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
Specifies that a **String** object is to be passed through to the pipeline representing the path to be added to the storage resource pool.

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
Specifies the path to be added to the storage resource pool.

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
Specifies the name of the resource pool to which the path is to be added.

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
Specifies the type of the resource pool for which storage paths are to be added.
Allowed values are **VFD**, **VHD**, and **ISO**.

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

[00000000-0000-0000-0000-000000000000](00000000-0000-0000-0000-000000000000)

