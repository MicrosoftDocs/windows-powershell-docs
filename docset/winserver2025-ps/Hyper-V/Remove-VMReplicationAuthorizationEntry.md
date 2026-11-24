---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.HyperV.PowerShell.Cmdlets.dll-Help.xml
Module Name: Hyper-V
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hyper-v/remove-vmreplicationauthorizationentry?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-VMReplicationAuthorizationEntry
---

# Remove-VMReplicationAuthorizationEntry

## SYNOPSIS
Removes an authorization entry from a Replica server.

## SYNTAX

### PrimaryServerName (Default)
```
Remove-VMReplicationAuthorizationEntry [-CimSession <CimSession[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential[]>] [-AllowedPrimaryServer] <String> [-Passthru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### TrustGroup
```
Remove-VMReplicationAuthorizationEntry [-CimSession <CimSession[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential[]>] [-TrustGroup] <String> [-Passthru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Object
```
Remove-VMReplicationAuthorizationEntry [-VMReplicationAuthorizationEntry] <VMReplicationAuthorizationEntry[]>
 [-Passthru] [-WhatIf] [-Confirm] [<CommonParameters>]
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

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: PrimaryServerName, TrustGroup
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName
Specifies one or more Hyper-V hosts on which the authorization entry is to be removed.
NetBIOS names, IP addresses, and fully qualified domain names are allowable.
The default is the local computer.
Use localhost or a dot (.) to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: PrimaryServerName, TrustGroup
Aliases:

Required: False
Position: Named
Default value: None
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

### -Credential
Specifies one or more user accounts that have permission to perform this action.
The default is the current user.

```yaml
Type: PSCredential[]
Parameter Sets: PrimaryServerName, TrustGroup
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Passthru
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### None
Default

### VMReplicationAuthorizationEntry
If **-PassThru** is specified.

## NOTES

## RELATED LINKS

