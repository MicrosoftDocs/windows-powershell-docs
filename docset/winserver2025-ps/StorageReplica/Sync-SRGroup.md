---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_WvrAdminTasks.cdxml-help.xml
Module Name: StorageReplica
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/storagereplica/sync-srgroup?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Sync-SRGroup
---

# Sync-SRGroup

## SYNOPSIS
Starts or resumes replication for a replication group.

## SYNTAX

```
Sync-SRGroup [[-ComputerName] <String>] [-Name] <String> [-Force] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Sync-SRGroup** cmdlet starts or resumes replication for a replication group.
If you pause replication, Storage Replica dismounts the volume.
Applications and users cannot access this volume  until you run **Sync-SRGroup**.

## EXAMPLES

### Example 1: Resume replication
```
PS C:\>Sync-SRGroup -Name "ReplicationGroup01"
```

This command resumes replication on the replication group named ReplicationGroup01.

## PARAMETERS

### -AsJob
Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to complete.

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
Specifies a single replica host computer NetBIOS name or fully qualified domain name (FQDN) of a computer for which this cmdlet syncs.
The default value is the local computer.

```yaml
Type: String
Parameter Sets: (All)
Aliases: CN

Required: False
Position: 0
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
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of the replication group for which this cmdlet starts or resumes replication.

If you pause replication, Storage Replica dismounts the volume.
Applications and users cannot access this volume until you run **Sync-SRGroup**.

```yaml
Type: String
Parameter Sets: (All)
Aliases: N

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ThrottleLimit
Specifies the maximum number of concurrent operations that can be established to run the cmdlet.
If this parameter is omitted or a value of `0` is entered, then Windows PowerShell® calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.
The throttle limit applies only to the current cmdlet, not to the session or to the computer.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-SRGroup](./Get-SRGroup.md)

[New-SRGroup](./New-SRGroup.md)

[Remove-SRGroup](./Remove-SRGroup.md)

[Set-SRGroup](./Set-SRGroup.md)

[Suspend-SRGroup](./Suspend-SRGroup.md)

