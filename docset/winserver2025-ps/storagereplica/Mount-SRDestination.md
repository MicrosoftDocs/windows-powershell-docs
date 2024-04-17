---
description: The Mount-SRDestination cmdlet mounts a snapshot of replicated storage temporarily for testing or backup purposes.
external help file: MSFT_WvrAdminTasks.cdxml-help.xml
Module Name: storagereplica
ms.date: 10/06/2021
online version: https://learn.microsoft.com/powershell/module/storagereplica/mount-srdestination?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Mount-SRDestination
---

# Mount-SRDestination

## SYNOPSIS
Mounts a snapshot of replicated storage temporarily for testing or backup purposes.

## SYNTAX

```
Mount-SRDestination [[-ComputerName] <String>] [-Name] <String> [-TemporaryPath] <String> [-Force]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Mount-SRDestination** cmdlet mounts a snapshot of replicated storage temporarily for testing or backup purposes.
Storage Replica dismounts the destination volume when replication begins.
Mounting the destination storage is called *test failover*.

Test failover requires an unused NTFS or ReFS formatted volume that isn't currently being replicated.

## EXAMPLES

### Example 1: Mount a snapshot of replicated storage
```powershell
Mount-SRDestination -ComputerName "SR-SRV05" -Name "ReplicationGroup01" -TemporaryPath T:\
```

This command sets up test failover for the replication group on the specified computer.

## PARAMETERS

### -AsJob
Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to complete.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: (All)
Aliases: Session

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName
Specifies a single replica host computer NetBIOS name or fully qualified domain name (FQDN).
The default value is the local computer.

```yaml
Type: String
Parameter Sets: (All)
Aliases: CN

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Force
Forces the command to run without asking for user confirmation.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: F

Required: False
Position: 100
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of the replication group for which this cmdlet mounts destination storage.

```yaml
Type: String
Parameter Sets: (All)
Aliases: N

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TemporaryPath
Specifies the path of the test failover volume.
This volume must be an unused NTFS or ReFS formatted volume that isn't currently replicating.

```yaml
Type: String
Parameter Sets: (All)
Aliases: D

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit
Specifies the maximum number of concurrent operations that can be established to run the cmdlet.
If this parameter is omitted or a value of `0` is entered, then Windows PowerShell calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.
The throttle limit applies only to the current cmdlet, not to the session or to the computer.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
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

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Dismount-SRDestination](Dismount-SRDestination.md)
