---
author: Kateyanne
external help file: Hyper-V_Cmdlets.xml
Module Name: Hyper-V
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/hyper-v/new-vmsan?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# New-VMSan

## SYNOPSIS
Creates a new virtual storage area network (SAN) on a Hyper-V host.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
New-VMSan [-Name] <String> [-ComputerName <String>] [-HostBusAdapter <CimInstance[]>] [-Note <String>]
 [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
New-VMSan [-Name] <String> [-ComputerName <String>] [-Note <String>] -WorldWideNodeName <String[]>
 -WorldWidePortName <String[]> [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **New-VMSan** cmdlet creates a new virtual storage area network (SAN) on a Hyper-V host.

## EXAMPLES

### Example 1
```
PS C:\>New-VMSan -Name Production -Note "Production SAN" -WorldWideNodeName C003FF0000FFFF00 -WorldWidePortName C003FF5778E50002
```

Creates a new virtual storage area network (SAN) with the specified Name, Note, WorldWideNodeName, and WorldWidePortName.

## PARAMETERS

### -ComputerName
Specifies the friendly name of a Hyper-V host on which the new virtual storage area network (SAN) is to be created.
NetBIOS names, IP addresses, and fully-qualified domain names are allowable.
The default is the local computer - use "localhost" or a dot (".") to specify the local computer explicitly.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: .
Accept pipeline input: False
Accept wildcard characters: False
```

### -HostBusAdapter
Specifies the host bus adapter (HBA) to be associated with the virtual storage area network (SAN) to be created.
This can be retrieved by running the Get-InitiatorPort cmdlet.

```yaml
Type: CimInstance[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the friendly name of the virtual storage area network (SAN) to be created.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Note
Specifies a note to be associated with the virtual storage area network (SAN) to be created.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WorldWideNodeName
Specifies the world wide node name (WWNN) of the host bus adapters to be associated with the virtual storage area network (SAN) to be created.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WorldWidePortName
Specifies the world wide port name (WWPN) of the host bus adapters to be associated with the virtual storage area network (SAN) to be created.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
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

## NOTES

## RELATED LINKS



