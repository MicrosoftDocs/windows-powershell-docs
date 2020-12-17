---
external help file: Hyper-V_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Enable-VMMigration

## SYNOPSIS
Enables migration on one or more virtual machine hosts.

## SYNTAX

```
Enable-VMMigration [[-ComputerName] <String[]>] [-Passthru]
```

## DESCRIPTION
The **Enable-VMMigration** cmdlet enables migration on one or more virtual machine hosts.

## EXAMPLES

### Example 1
```
PS C:\>Enable-VMMigration
```

Enables live migration on the local Hyper-V host.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts on which migration is to be enabled.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: .
Accept pipeline input: False
Accept wildcard characters: False
```

### -Passthru
Specifies that a **Microsoft.Virtualization.Powershell.Host** object is to be passed through to the pipeline representing each virtual machine host on which migration is to be enabled.

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

### Microsoft.Virtualization.Powershell.Host
If **-PassThru** is specified.

## NOTES

## RELATED LINKS



