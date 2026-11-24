---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_WvrAdminTasks.cdxml-help.xml
Module Name: StorageReplica
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/storagereplica/get-srnetworkconstraint?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-SRNetworkConstraint
---

# Get-SRNetworkConstraint

## SYNOPSIS
Gets replication network constraints for Storage Replica partnerships.

## SYNTAX

```
Get-SRNetworkConstraint [[-SourceComputerName] <String>] [[-SourceRGName] <String>]
 [[-DestinationComputerName] <String>] [[-DestinationRGName] <String>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SRNetworkConstraint** cmdlet gets replication network constraints for Storage Replica partnerships.
You can apply network constraints to one or more network adapter interfaces to control which networks Storage Replica can use.
By default, Storage Replica uses networks according to the rules of SMB Multichannel.
Network constraints are an allowed list.

## EXAMPLES

### Example 1: Display replication network constraints for all partnerships
```
PS C:\>Get-SRNetworkConstraint
DestinationComputerName : SR-SRV06
DestinationNWInterface  : {6}
DestinationRGName       : ReplicationGroup02
SourceComputerName      : SR-SRV05
SourceNWInterface       : {2}
SourceRGName            : ReplicationGroup01
PSComputerName          :
```

This command displays all replication network constraints for all partnerships.

### Example 2: Display a replication network constraint
```
PS C:\>Get-SRNetworkConstraint -SourceRGName "ReplicationGroup01" -SourceComputerName "SR-SRV05"
DestinationComputerName : SR-SRV06
DestinationNWInterface  : {6}
DestinationRGName       : ReplicationGroup02
SourceComputerName      : SR-SRV05
SourceNWInterface       : {2}
SourceRGName            : ReplicationGroup01
PSComputerName          :
```

This command displays the network constraint for the replication group named ReplicationGroup01 for a specific computer.

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

### -DestinationComputerName
Specifies a single replica host computer NetBIOS name or fully qualified domain name (FQDN) of the destination computer for which this cmdlet gets constraints.
The default value is the local computer.

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
Specifies the name of a destination replication group for which this cmdlet gets constraints.

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

### -SourceComputerName
Specifies a single replica host computer NetBIOS name or FQDN of the source computer for which this cmdlet gets constraints.
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
Specifies the name of the source replication group for which this cmdlet gets constraints.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Remove-SRNetworkConstraint](./Remove-SRNetworkConstraint.md)

[Set-SRNetworkConstraint](./Set-SRNetworkConstraint.md)

