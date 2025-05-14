---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_WvrAdminTasks.cdxml-help.xml
Module Name: StorageReplica
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/storagereplica/remove-srnetworkconstraint?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-SRNetworkConstraint
---

# Remove-SRNetworkConstraint

## SYNOPSIS
Removes all existing replication network constraints.

## SYNTAX

```
Remove-SRNetworkConstraint [[-SourceComputerName] <String>] [[-SourceRGName] <String>]
 [[-DestinationComputerName] <String>] [[-DestinationRGName] <String>] [-Force] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-SRNetworkConstraint** cmdlet removes all current replication network constraints for the specified servers and replication groups.
Network constraints are not iterative.
To modify constraints, use the Set-SRNetworkConstraint cmdlet.

## EXAMPLES

### Example 1: Remove all network constraints
```
PS C:\>Remove-SRNetworkConstraint -SourceComputerName "SR-SRV05" -SourceRGName "ReplicationGroup01" -DestinationComputerName "SR-SRV06" -DestinationRGName "ReplicationGroup02"
```

This command removes all network constraints between two computers named SR-SRV05 and SR-SRV06 and the specified replication groups.
Network constraint settings are never iterative.

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
Specifies a single replica host computer NetBIOS name or fully qualified domain name (FQDN) of the destination computer.

```yaml
Type: String
Parameter Sets: (All)
Aliases: DCN

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DestinationRGName
Specifies the name of the destination replication group for which this cmdlet removes a constraint.

```yaml
Type: String
Parameter Sets: (All)
Aliases: DGN

Required: False
Position: 3
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

### -SourceComputerName
Specifies a single replica host computer NetBIOS name or FQDN of the source computer for which this cmdlet removes a constraint.
The default value is the local computer.

```yaml
Type: String
Parameter Sets: (All)
Aliases: SCN

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SourceRGName
Specifies the name of the source replication group for which this cmdlet removes a constraint.

```yaml
Type: String
Parameter Sets: (All)
Aliases: SGN

Required: False
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

[Get-SRNetworkConstraint](./Get-SRNetworkConstraint.md)

[Set-SRNetworkConstraint](./Set-SRNetworkConstraint.md)

