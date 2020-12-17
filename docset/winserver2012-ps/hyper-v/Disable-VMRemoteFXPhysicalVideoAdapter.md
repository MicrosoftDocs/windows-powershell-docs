---
external help file: Hyper-V_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Disable-VMRemoteFXPhysicalVideoAdapter

## SYNOPSIS
Disables one or more RemoteFX physical video adapters from use with RemoteFX-enabled virtual machines.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Disable-VMRemoteFXPhysicalVideoAdapter [-Name] <String[]> [-ComputerName <String[]>] [-Passthru]
```

### UNNAMED_PARAMETER_SET_2
```
Disable-VMRemoteFXPhysicalVideoAdapter [-GPU] <VMRemoteFXPhysicalVideoAdapter[]> [-Passthru]
```

## DESCRIPTION
The **Disable-VMRemoteFXPhysicalVideoAdapter** disables one or more RemoteFX physical video adapter from use with RemoteFX-enabled virtual machines.

## EXAMPLES

### Example 1
```
PS C:\>Disable-VMRemoteFXPhysicalVideoAdapter -Name *Nvidia*
```

This example disables all RemoteFX physical video adapters that include the string "Nvidia" in their names.

### Example 2
```
PS C:\>Get-VMRemoteFXPhysicalVideoAdapter -Name *Nvidia* | Disable-VMRemotePhysicalVideoAdapter
```

This example disables all RemoteFX physical video adapters that include the string "Nvidia" in their names.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts on which the RemoteFX physical video adapters are to be disabled.
NetBIOS names, IP addresses, and fully-qualified domain names are allowable.
The default is the local computer - use "localhost" or a dot (".") to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GPU
Specifies one or more RemoteFX physical video adapters to disable.

```yaml
Type: VMRemoteFXPhysicalVideoAdapter[]
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Passthru
Specifies that **Microsoft.HyperV.PowerShell.VMRemoteFXPhysicalVideoAdapter** objects are to be passed to the pipeline representing the RemoteFX physical video adapters to be disabled.

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

### -Name


```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

## INPUTS

### Microsoft.HyperV.PowerShell.VMRemoteFXPhysicalVideoAdapter[]

### System.String[]

## OUTPUTS

### None
Default

### Microsoft.HyperV.PowerShell.VMRemoteFXPhysicalVideoAdapter
If **-PassThru** is specified.

## NOTES

## RELATED LINKS



