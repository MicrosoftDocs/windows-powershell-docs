---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.HyperV.PowerShell.Cmdlets.dll-Help.xml
Module Name: Hyper-V
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hyper-v/get-vmreplicationauthorizationentry?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-VMReplicationAuthorizationEntry
---

# Get-VMReplicationAuthorizationEntry

## SYNOPSIS
Gets the authorization entries of a Replica server.

## SYNTAX

```
Get-VMReplicationAuthorizationEntry [[-AllowedPrimaryServer] <String>] [-ReplicaStorageLocation <String>]
 [-TrustGroup <String>] [-CimSession <CimSession[]>] [-ComputerName <String[]>] [-Credential <PSCredential[]>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-VMReplicationAuthorizationEntry** cmdlet gets the replication authorization entries specified for a Replica server.

## EXAMPLES

### Example 1
```
PS C:\> Get-VMReplicationAuthorizationEntry
```

This example gets the replication authorization entries  for the local Replica server.

### Example 2
```
PS C:\> Get-VMReplicationAuthorizationEntry server01.domain01.contoso.com
```

This example gets the replication authorization entry for an allowed primary server named server01.domain01.contoso.com.

## PARAMETERS

### -AllowedPrimaryServer
Specifies the allowed primary server for which replication authorization entries are to be retrieved.

```yaml
Type: String
Parameter Sets: (All)
Aliases: AllowedPS

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName
Specifies one or more Hyper-V hosts from which replication authorization entries are to be retrieved.
NetBIOS names, IP addresses, and fully qualified domain names are allowable.
The default is the local computer.
Use localhost or a dot (.) to specify the local computer explicitly.

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

### -Credential
Specifies one or more user accounts that have permission to perform this action.
The default is the current user.

```yaml
Type: PSCredential[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ReplicaStorageLocation
Specifies the location where virtual hard disk files are stored when an authorized primary server sends replication data to the specified Replica server.

```yaml
Type: String
Parameter Sets: (All)
Aliases: StorageLoc

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TrustGroup
Gets the replication authorization entries that have the specified value for TrustGroup.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.HyperV.PowerShell.VMReplicationAuthorizationEntry

## NOTES

## RELATED LINKS

