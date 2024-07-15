---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_WvrAdminTasks.cdxml-help.xml
Module Name: StorageReplica
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/storagereplica/remove-srpartnership?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-SRPartnership
---

# Remove-SRPartnership

## SYNOPSIS
Removes a replication partnership.

## SYNTAX

```
Remove-SRPartnership [[-SourceComputerName] <String>] [-SourceRGName] <String>
 [-DestinationComputerName] <String> [-DestinationRGName] <String> [-ApplyChanges] [-IgnoreRemovalFailure]
 [-Force] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Remove-SRPartnership** cmdlet removes an existing replication partnership.
A partnership is the replication relationship between replication groups on a pair of servers, a pair of clusters, or nodes in a stretch cluster.

## EXAMPLES

### Example 1: Remove a partnership
```
PS C:\>Remove-SRPartnership -SourceComputerName "SR-SRV05" -SourceRGName "ReplicationGroup01" -DestinationComputerName "SR-SRV06" -DestinationRGName "ReplicationGroup02"
Confirm
Are you sure you want to perform this action?
This action will remove partnership between source group ReplicationGroup01 and destination group ReplicationGroup02.
 Are you sure you want to continue?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"):
```

This command removes a partnership between servers SR-SRV05 and SR-SRV06.

### Example 2: Remove all partnerships
```
PS C:\>Get-SRPartnership | Remove-SRPartnership
Confirm
Are you sure you want to perform this action?
This action will remove partnership between source group ReplicationGroup01 and destination group ReplicationGroup02.
 Are you sure you want to continue?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"):
```

This command gets all partnerships on the current computer by using the Get-SRPartnership cmdlet.
The command passes the partnerships to the current cmdlet by using the pipeline operator.
The current cmdlet removes all partnerships for all paired servers.

## PARAMETERS

### -ApplyChanges
Indicates that the cmdlet applies changes.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: ADA

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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

### -DestinationComputerName
Specifies a single replica host computer NetBIOS name or fully qualified domain name (FQDN) of the destination computer for which this cmdlet removes a partnership.

```yaml
Type: String
Parameter Sets: (All)
Aliases: DCN

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DestinationRGName
Specifies the name of the destination replication group for which this cmdlet removes a partnership.

```yaml
Type: String
Parameter Sets: (All)
Aliases: DGN

Required: True
Position: 4
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

### -IgnoreRemovalFailure
Indicates that this cmdlet removes the partnership even if both computers are not online.
Specify this parameter only if a disaster has made one of the computers permanently unreachable.
Otherwise, the other computer may continue to believe it is in a partnership.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: IRF

Required: False
Position: 99
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SourceComputerName
Specifies a single replica host computer NetBIOS name or FQDN of the source computer for which this cmdlet removes a partnership.
The default value is the local computer.

```yaml
Type: String
Parameter Sets: (All)
Aliases: SCN

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -SourceRGName
Specifies the name of the source replication group for which this cmdlet removes a partnership.

```yaml
Type: String
Parameter Sets: (All)
Aliases: SGN

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

## NOTES

## RELATED LINKS

[Get-SRPartnership](./Get-SRPartnership.md)

[New-SRPartnership](./New-SRPartnership.md)

[Set-SRPartnership](./Set-SRPartnership.md)

