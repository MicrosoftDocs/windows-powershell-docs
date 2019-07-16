---
external help file: Hyper-V_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-anbarr
author: andreabarr
---

# Get-VMRemoteFXPhysicalVideoAdapter

## SYNOPSIS
Gets the RemoteFX physical graphics adapters on one or more Hyper-V hosts.

## SYNTAX

```
Get-VMRemoteFXPhysicalVideoAdapter [[-Name] <String[]>] [-ComputerName <String[]>]
```

## DESCRIPTION
The **Get-VMRemoteFXPhysicalVideoAdapter** cmdlet gets the RemoteFX physical graphics adapters on one or more Hyper-V hosts.

## EXAMPLES

### Example 1
```
PS C:\>Get-VMRemoteFXPhysicalVideoAdapter
```

Gets all RemoteFX physical video adapters on the Hyper-V host.

### Example 2
```
PS C:\>Get-VMRemoteFXPhysicalVideoAdapter -Name *Nvidia*
```

Gets all RemoteFX physical video adapters on the Hyper-V host which include the sequence Nvidia in their name.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts from which the RemoteFX physical graphics adapters are to be retrieved.
NetBIOS names, IP addresses, and fully-qualified domain names are allowable.
The default is the local computer - use "localhost" or a dot (".") to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: .
Accept pipeline input: True (ByValue, ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the names of one or more RemoteFX physical graphics adapters to be retrieved.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: True
```

## INPUTS

## OUTPUTS

### Microsoft.HyperV.PowerShell.VMRemoteFXPhysicalVideoAdapter[]

## NOTES

## RELATED LINKS

[00000000-0000-0000-0000-000000000000](00000000-0000-0000-0000-000000000000)

