---
external help file: Hyper-V_Cmdlets.xml
Module Name: Hyper-V
online version: https://learn.microsoft.com/powershell/module/hyper-v/disconnect-vmsan?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Disconnect-VMSan

## SYNOPSIS
Removes a host bus adapter from a virtual storage area network (SAN).

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Disconnect-VMSan [-Name] <String> [-ComputerName <String[]>] [-Passthru] -WorldWideNodeName <String[]>
 -WorldWidePortName <String[]>
```

### UNNAMED_PARAMETER_SET_2
```
Disconnect-VMSan [-Name] <String> [-Passthru] -HostBusAdapter <CimInstance[]>
```

## DESCRIPTION
The **Disconnect-VMSan** cmdlet removes a host bus adapter from a virtual storage area network (SAN).

## EXAMPLES

### Example 1
```
PS C:\>Disconnect-VMSan -Name Production -WorldWideNodeName C003FF0000FFFF00 -WorldWidePortName C003FF5778E50002
```

Removes the host bus adapter having the specified world wide node name and world wide port name from the virtual machine named Production on the local Hyper-V host.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts on which a host bus adapter is to be removed from a virtual storage area network (SAN).
NetBIOS names, IP addresses, and fully-qualified domain names are allowable.
The default is the local computer - use "localhost" or a dot (".") to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: .
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -HostBusAdapter
Specifies the host bus adapter to be removed from the virtual storage area network (SAN).

```yaml
Type: CimInstance[]
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Specifies the name of the virtual storage area network (SAN) from which the host bus adapter is to be removed.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Passthru
Specifies that an object is to be passed through to the pipeline representing the virtual storage area network (SAN) from which the host bus adapter is to be removed.

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

### -WorldWideNodeName
The world wide node name of the host bus adapter to be removed from the virtual storage area network (SAN).

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WorldWidePortName
The world wide port name of the host bus adapter to be removed from the virtual storage area network (SAN).

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

### None
Default

### VMSan
If **-PassThru** is specified.

## NOTES

## RELATED LINKS



