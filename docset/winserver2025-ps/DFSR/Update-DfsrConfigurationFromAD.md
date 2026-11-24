---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: DfsrPowerShell.dll-Help.xml
Module Name: DFSR
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dfsr/update-dfsrconfigurationfromad?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Update-DfsrConfigurationFromAD
---

# Update-DfsrConfigurationFromAD

## SYNOPSIS
Initiates an update of the DFS Replication service.

## SYNTAX

```
Update-DfsrConfigurationFromAD [[-ComputerName] <String[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Update-DfsrConfigurationFromAD** cmdlet initiates an update of the Distributed File System (DFS) Replication service.
The cmdlet forces the DFS Replication service to immediately perform a full Lightweight Directory Access Protocol (LDAP) poll of the Active Directory Domain Services (AD DS) for configuration changes, and applies any changes to the service.

By default, the DFS Replication service queries domain controllers every five minutes by using a lightweight check for membership configuration changes in AD DS.
This periodic check speeds up the service response to certain types of configuration changes.
If the DFS Replication service detects a new membership, a full poll follows.
By default, the DFS Replication service performs a full poll every hour.

## EXAMPLES

### Example 1: Update the DFS Replication service
```
PS C:\> Update-DfsrConfigurationFromAD -ComputerName "SRV01","SRV02" -Verbose


VERBOSE: Performing operation "Update-DfsrConfigurationFromAD" on Target "SRV01".
VERBOSE: Successfully updated the DFSR Active Directory Domain Service configuration on the computer named SRV01.
VERBOSE: Performing operation "Update-DfsrConfigurationFromAD" on Target "SRV02".
VERBOSE: Successfully updated the DFSR Active Directory Domain Service configuration on the computer named SRV02.
```

This command forces the remote DFS Replication servers SRV01 and SRV02 to poll AD DS immediately and apply any changes to the DFS Replication service.

## PARAMETERS

### -ComputerName
Specifies an array of names of member computers.
You can use a comma separated list and the wildcard character (*).
The cmdlet forces the DFS Replication service on the computers to poll Active Directory immediately.

If you do not specify this parameter, the cmdlet uses the local computer.
To return a response, use the *Verbose* parameter.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: MemberList, MemList

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### String

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Get-DfsrMember](./Get-DfsrMember.md)

