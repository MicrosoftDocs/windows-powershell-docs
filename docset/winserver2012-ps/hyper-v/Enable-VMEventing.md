---
external help file: Hyper-V_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-anbarr
author: andreabarr
---

# Enable-VMEventing

## SYNOPSIS
Enables virtual machine eventing.

## SYNTAX

```
Enable-VMEventing [-ComputerName <String[]>] [-Force]
```

## DESCRIPTION
The **Enable-VMEventing** cmdlet enables virtual machine eventing.
Virtual machine eventing keeps Hyper-V PowerShell objects updated without polling the virtual machine host.
Virtual machine eventing is enabled by default.

## EXAMPLES

### Example 1
```
PS C:\>Enable-VMEventing -Force
```

Enables virtual machine eventing, suppressing the confirmation prompt.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts on which virtual machine eventing is to be enabled.
NetBIOS names, IP addresses, and fully-qualified domain names are allowable.
The default is the local computer - use "localhost" or a dot (".") to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
Specifies that the confirmation prompt is to be suppressed.
(This is useful in scripting the cmdlet.)

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

## NOTES

## RELATED LINKS

[00000000-0000-0000-0000-000000000000](00000000-0000-0000-0000-000000000000)

