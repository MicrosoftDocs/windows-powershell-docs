---
author: Kateyanne
external help file: Hyper-V_Cmdlets.xml
Module Name: Hyper-V
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/hyper-v/get-vmreplicationserver?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-VMReplicationServer

## SYNOPSIS
Gets the replication and authentication settings of a Replica server.

## SYNTAX

```
Get-VMReplicationServer [[-ComputerName] <String[]>]
```

## DESCRIPTION
The **Get-VMReplicationServer** cmdlet gets the replication and authentication settings of a Replica server.

## EXAMPLES

### Example 1
```
PS C:\> Get-VMReplicationServer
```

This example gets the replication configuration of the local Replica server.

### Example 2
```
PS C:\> Get-VMReplicationServer server01.domain01.contoso.com
```

This example gets the replication configuration of a server named server01.domain01.contoso.com.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts for which to retrieve replication and authentication settings.
NetBIOS names, IP addresses, and fully-qualified domain names are allowable.
The default is the local computer - use "localhost" or a dot (".") to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: .
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

### VMReplicationServer

## NOTES

## RELATED LINKS



