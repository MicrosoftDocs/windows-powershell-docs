---
external help file: Hyper-V_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-anbarr
author: andreabarr
---

# Get-VMSystemSwitchExtension

## SYNOPSIS
Gets the switch extensions installed on a virtual machine host.

## SYNTAX

```
Get-VMSystemSwitchExtension [-ComputerName <String[]>] [-Name <String[]>]
```

## DESCRIPTION
The **Get-VMSystemSwitchExtension** cmdlet gets the switch extensions installed on a virtual machine host.
The returned switch extension does not contain embedded objects for features or an array of feature IDs.

## EXAMPLES

### Example 1
```
PS C:\>Get-VMSystemSwitchExtension
```

Gets all virtual switch extensions installed on the system.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts from which the switch extensions are to be retrieved.
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

### -Name
Specifies the name of the switch extension to be retrieved.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

## INPUTS

## OUTPUTS

### Microsoft.Virtualization.Powershell.SystemSwitchExtension

## NOTES

## RELATED LINKS

[00000000-0000-0000-0000-000000000000](00000000-0000-0000-0000-000000000000)

