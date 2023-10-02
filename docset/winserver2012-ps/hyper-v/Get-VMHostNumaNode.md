---
external help file: Hyper-V_Cmdlets.xml
Module Name: Hyper-V
online version: https://learn.microsoft.com/powershell/module/hyper-v/get-vmhostnumanode?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-VMHostNumaNode

## SYNOPSIS
Gets the NUMA topology of a virtual machine host.

## SYNTAX

```
Get-VMHostNumaNode [[-ComputerName] <String[]>] [-Id <Int32>]
```

## DESCRIPTION
The **Get-MVHostNumaNode** cmdlet gets the NUMA topology of a Hyper-V host, returning a **VMHostNumaNode** object for each of the host's NUMA nodes.

## EXAMPLES

### Example 1
```
PS C:\>Get-VMHostNumaNode
```

Gets the NUMA topology of the local Hyper-V host.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts for which the NUMA topology is to be retrieved.
NetBIOS names, IP addresses, and fully-qualified domain names are allowable.
The default is the local computer - use "localhost" or a dot (".") to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: .
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Id
Identifies a NUMA node for which a **VMHostNumaNode** is to be retrieved.

```yaml
Type: Int32
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



