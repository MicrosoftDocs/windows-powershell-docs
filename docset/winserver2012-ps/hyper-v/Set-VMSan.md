---
external help file: Hyper-V_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Set-VMSan

## SYNOPSIS
Configures a virtual storage area network (SAN) on one or more Hyper-V hosts.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Set-VMSan [-Name] <String> [-HostBusAdapter <CimInstance[]>] [-Note <String>] [-Passthru]
```

### UNNAMED_PARAMETER_SET_2
```
Set-VMSan [-Name] <String> [-ComputerName <String[]>] [-Note <String>] [-Passthru]
 -WorldWideNodeName <String[]> -WorldWidePortName <String[]>
```

## DESCRIPTION
The **Set-VMSan** cmdlet configures a virtual storage area network (SAN) on one or more Hyper-V hosts.

## EXAMPLES

### Example 1
```
PS C:\>Set-VMSan -Name Production -WorldWideNodeName C003FF0000FFFF22 -WorldWidePortName C003FF5778E50024
```

Configures a virtual storage area network (SAN) named Production with the specified WorldWideNodeName and WorldWidePortName values.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts on which the virtual storage area network (SAN) is to be configured.
NetBIOS names, IP addresses, and fully-qualified domain names are allowable.
The default is the local computer - use "localhost" or a dot (".") to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: Named
Default value: .
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -HostBusAdapter
Specifies the Fibre Channel host bus adapter to be associated with the virtual storage area network (SAN).

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
Specifies the name of the virtual storage area network (SAN) to be configured.

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

### -Note
Specifies the note to be associated with the virtual storage area network (SAN).

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

### -Passthru
Specifies that an object is to be passed through to the pipeline representing the configured virtual storage area network (SAN).

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
The World Wide Node name of the Fibre Channel host bus adapter to be associated with this virtual storage area network (SAN).

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
The World Wide Port name of the Fibre Channel host bus adapter to be associated with this virtual storage area network (SAN).

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

## INPUTS

## OUTPUTS

### None
Default

### Microsoft.Virtualization.PowerShell.SAN
If **-PassThru** is specified.

## NOTES

## RELATED LINKS



