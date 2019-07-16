---
external help file: Hyper-V_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-anbarr
author: andreabarr
---

# Get-VMHost

## SYNOPSIS
Gets a Hyper-V host.

## SYNTAX

```
Get-VMHost [[-ComputerName] <String[]>]
```

## DESCRIPTION
The **Get-VMHost** cmdlet gets a Hyper-V host.

## EXAMPLES

### Example 1
```
PS C:\>Get-VMHost
```

Gets the local Hyper-V host.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts to be retrieved.
NetBIOS names, IP addresses, and fully-qualified domain names are allowable.
The default is the local computer - use "localhost" or a dot (".") to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: .
Accept pipeline input: True (ByValue, ByPropertyName)
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

### Microsoft.Virtualization.Powershell.Host

## NOTES

## RELATED LINKS

[00000000-0000-0000-0000-000000000000](00000000-0000-0000-0000-000000000000)

