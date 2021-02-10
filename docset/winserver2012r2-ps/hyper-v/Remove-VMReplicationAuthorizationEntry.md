---
external help file: Microsoft.HyperV.PowerShell.dll-Help.xml
Module Name: Hyper-V
online version: 
schema: 2.0.0
title: Remove-VMReplicationAuthorizationEntry
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 841B0143-884A-4E5A-BA85-300A9C86E6EF
---

# Remove-VMReplicationAuthorizationEntry

## SYNOPSIS
Removes an authorization entry from a Replica server.

## SYNTAX

### PrimaryServerName (Default)
```
Remove-VMReplicationAuthorizationEntry [-ComputerName <String[]>] [-AllowedPrimaryServer] <String> [-PassThru]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### TrustGroup
```
Remove-VMReplicationAuthorizationEntry [-ComputerName <String[]>] [-TrustGroup] <String> [-PassThru] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### Object
```
Remove-VMReplicationAuthorizationEntry [-VMReplicationAuthorizationEntry] <VMReplicationAuthorizationEntry[]>
 [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-VMReplicationAuthorizationEntry** cmdlet removes an authorization entry from a Replica server, which cancels authorization for the primary server associated with the entry.
After the authorization entry is removed, the Replica server does not accept replication data from the corresponding primary server.

## EXAMPLES

### Example 1
```
PS C:\> Remove-VMReplicationAuthorizationEntry -AllowedPrimaryServer server01.domain01.contoso.com
```

This example removes an authorization entry on the local Replica server for allowed primary server server01.domain01.contoso.com.

### Example 2
```
PS C:\> Get-VMReplicationAuthorizationEntry | Remove-VMReplicationAuthorizationEntry
```

This example removes all authorization entries on the local Replica server.

## PARAMETERS

### -AllowedPrimaryServer
Specifies the allowed primary server for which the authorization entry is to be removed.

```yaml
Type: String
Parameter Sets: PrimaryServerName
Aliases: AllowedPS

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ComputerName
Specifies one or more Hyper-V hosts on which the authorization entry is to be removed.
NetBIOS names, IP addresses, and fully-qualified domain names are allowable.
The default is the local computer - use "localhost" or a dot (".") to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: PrimaryServerName, TrustGroup
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
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Specifies that a **VMReplicationAuthorizationEntry** object is to be passed through to the pipeline representing the authorization entry to be removed.

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

### -TrustGroup
Specifies the trust group for which the authorization entries are to be removed.

```yaml
Type: String
Parameter Sets: TrustGroup
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMReplicationAuthorizationEntry
Specifies the authorization entry to be removed.

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
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
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

