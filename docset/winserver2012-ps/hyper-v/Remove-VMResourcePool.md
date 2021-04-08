---
author: Kateyanne
external help file: Hyper-V_Cmdlets.xml
Module Name: Hyper-V
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/hyper-v/remove-vmresourcepool?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Remove-VMResourcePool

## SYNOPSIS
Deletes a resource pool from one or more virtual machine hosts.

## SYNTAX

```
Remove-VMResourcePool [-Name] <String> [-ResourcePoolType] <VMResourcePoolType[]> [-ComputerName <String[]>]
 [-Passthru] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Remove-VMResourcePool** deletes a resource pool from one or more virtual machine hosts.

## EXAMPLES

### Example 1
```
PS C:\>Remove-VMResourcePool Test VHD
```

Removes a virtual hard disk resource pool named Test.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts on which the resource pool is to be deleted.
NetBIOS names, IP addresses, and fully-qualified domain names are allowable.
The default is the local computer - use "localhost" or a dot (".") to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: .
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the name of the resource pool.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -Passthru
Specifies that a **VMResourcePool** object is to be passed through to the pipeline representing the removed resource pool.

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

### -ResourcePoolType
Specifies the type of the resource pool to be deleted.

```yaml
Type: VMResourcePoolType[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

### None
Default

### VMResourcePool
If **-PassThru** is specified.

## NOTES

## RELATED LINKS



