---
external help file: Microsoft.HyperV.PowerShell.dll-Help.xml
Module Name: Hyper-V
ms.date: 10/30/2017
online version: https://docs.microsoft.com/powershell/module/hyper-v/get-vmreplicationserver?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-VMReplicationServer
---

# Get-VMReplicationServer

## SYNOPSIS
Gets the replication and authentication settings of a Replica server.

## SYNTAX

```
Get-VMReplicationServer [[-ComputerName] <String[]>] [<CommonParameters>]
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
Position: 0
Default value: .
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### VMReplicationServer

## NOTES

## RELATED LINKS

