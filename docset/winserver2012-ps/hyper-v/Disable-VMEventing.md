---
external help file: Hyper-V_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Disable-VMEventing

## SYNOPSIS
Disables virtual machine eventing.

## SYNTAX

```
Disable-VMEventing [-ComputerName <String[]>] [-Force] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Disable-VMEventing** cmdlet disables virtual machine eventing on a Hyper-V host or hosts.
Virtual machine eventing keeps Hyper-V PowerShell objects updated without polling the virtual machine host.
Virtual machine eventing is enabled by default.

## EXAMPLES

### Example 1
```
PS C:\>Disable-VMEventing -Force
```

Disables virtual machine eventing, suppressing the confirmation prompt.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts on which virtual machine eventing is to be disabled.
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



