---
external help file: Hyper-V_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Remove-VMSan

## SYNOPSIS
Removes a virtual storage area network (SAN) from a Hyper-V host.

## SYNTAX

```
Remove-VMSan [-Name] <String[]> [-ComputerName <String[]>] [-Passthru]
```

## DESCRIPTION
The **Remove-VMSan** cmdlet removes a virtual storage area network (SAN) from a Hyper-V host.

## EXAMPLES

### Example 1
```
PS C:\>Remove-VMSan -Name Production
```

Removes the virtual storage area network named Production from the local Hyper-V host.

## PARAMETERS

### -ComputerName
Specifies a Hyper-V host from which the virtual storage area network (SAN) is to be removed.
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
Specifies the name of the virtual storage area network (SAN) to be removed from the Hyper-V host.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Passthru
Specifies that an object is to be passed through to the pipeline representing the removed virtual machine storage area network.

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

## INPUTS

## OUTPUTS

### None
Default

### Microsoft.Virtualization.Powershell.SAN
If **-PassThru** is specified.

## NOTES

## RELATED LINKS



