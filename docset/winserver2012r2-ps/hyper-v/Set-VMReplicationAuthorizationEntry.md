---
author: Kateyanne
description: 
external help file: Microsoft.HyperV.PowerShell.dll-Help.xml
manager: jasgro
Module Name: Hyper-V
ms.author: v-kaunu
ms.date: 10/30/2017
ms.prod: powershell
ms.reviewer: brianlic
ms.topic: reference
online version: https://docs.microsoft.com/powershell/module/hyper-v/set-vmreplicationauthorizationentry?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-VMReplicationAuthorizationEntry
---

# Set-VMReplicationAuthorizationEntry

## SYNOPSIS
Modifies an authorization entry on a Replica server.

## SYNTAX

### Name (Default)
```
Set-VMReplicationAuthorizationEntry [-ComputerName <String[]>] [-AllowedPrimaryServer] <String>
 [[-ReplicaStorageLocation] <String>] [[-TrustGroup] <String>] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### Object
```
Set-VMReplicationAuthorizationEntry [-VMReplicationAuthorizationEntry] <VMReplicationAuthorizationEntry[]>
 [[-ReplicaStorageLocation] <String>] [[-TrustGroup] <String>] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-VMReplicationAuthorizationEntry** cmdlet modifies an authorization entry on Replica server.

## EXAMPLES

### Example 1
```
PS C:\> Set-VMReplicationAuthorizationEntry server01.domain01.contoso.com -ReplicaStorageLocation "D:\NewStorageLocation"
```

This example sets the location of the replication authorization entry for allowed primary server server01.domain01.contoso.com to location D:\NewStorageLocation.

### Example 2
```
PS C:\> Set-VMReplicationAuthorizationEntry server01.domain01.contoso.com -TrustGroup TrustGroup01
```

This example sets the trust group of the replication authorization entry for allowed primary server server01.domain01.contoso.com to TrustGroup01.

## PARAMETERS

### -AllowedPrimaryServer
Specifies the allowed primary server of the authorization entry to be modified.

```yaml
Type: String
Parameter Sets: Name
Aliases: AllowedPS

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ComputerName
Specifies one or more Hyper-V hosts on which the authorization entry is to be set.
NetBIOS names, IP addresses, and fully-qualified domain names are allowable.
The default is the local computer - use "localhost" or a dot (".") to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: Name
Aliases: 

Required: False
Position: Named
Default value: .
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Specifies that an object is to be passed through to the pipeline representing the replication authorization entry to be set.

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

### -ReplicaStorageLocation
Specifies the location to store the Replica virtual hard disk files from the allowed server when a new Replica virtual machine is created.
Modifying this location does not affect any existing virtual hard disk files on the Replica server.

```yaml
Type: String
Parameter Sets: (All)
Aliases: StorageLoc

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TrustGroup
Identifies a group of primary servers within which a given primary virtual machine can move so replications of the primary virtual machine are accepted by the Replica server only from primary servers that belong to the trust group.
You can use any string to create a new trust group.
Ensure all primary servers within a specific trust group use the same string as the value you specify for this parameter.

Use of a trust group can help you keep virtual machines isolated by maintaining control over which primary servers are trusted to provide replication, while also allowing the virtual machines to move from one primary server to another (such as through live migration or failover from a cluster node).

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMReplicationAuthorizationEntry
Specifies the authorization entry to be set.

```yaml
Type: VMReplicationAuthorizationEntry[]
Parameter Sets: Object
Aliases: VMRepAuthEntry

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs. The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

###  
None by default; **VMReplicationAuthorizationEntry** if **-PassThru** is specified.

## NOTES

## RELATED LINKS

