---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_WvrAdminTasks.cdxml-help.xml
Module Name: StorageReplica
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/storagereplica/get-srpartnership?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-SRPartnership
---

# Get-SRPartnership

## SYNOPSIS
Gets replication partnerships.

## SYNTAX

### NonCluster (Default)
```
Get-SRPartnership [[-SourceComputerName] <String>] [[-SourceRGName] <String>]
 [[-DestinationComputerName] <String>] [[-DestinationRGName] <String>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### FromGroup
```
Get-SRPartnership [[-ComputerName] <String>] [[-Name] <String>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SRPartnership** cmdlet gets existing replication partnerships.
A partnership is the replication relationship between replication groups on a pair of servers, a pair of clusters, or nodes in a stretch cluster.

## EXAMPLES

### Example 1: Get all partnerships on a computer
```
PS C:\>Get-SRPartnership
DestinationComputerName : SR-SRV06
DestinationRGName       : ReplicationGroup02
Id                      : 084afd15-3340-4695-9f9a-5fdc666a89c6
SourceComputerName      : SR-SRV05
SourceRGName            : ReplicationGroup01
PSComputerName          :
```

This command gets all partnerships on the local computer.

### Example 2: Get partnerships between two servers
```
PS C:\>Get-SRPartnership -SourceComputerName "SR-SRV05" -DestinationComputerName "SR-SRV06"
DestinationComputerName : SR-SRV06
DestinationRGName       : ReplicationGroup02
Id                      : 084afd15-3340-4695-9f9a-5fdc666a89c6
SourceComputerName      : SR-SRV05
SourceRGName            : ReplicationGroup01
PSComputerName          :
```

This command gets all partnerships between the strand-alone servers named SR-SRV05 and SR-SRV06.

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
Specifies a single replica host computer NetBIOS name or fully qualified domain name (FQDN) of a computer on which this cmdlet gets partnerships.

```yaml
Type: String
Parameter Sets: FromGroup
Aliases: CN

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DestinationComputerName
Specifies a single replica host computer NetBIOS name or FQDN of the destination computer for which this cmdlet gets partnerships.

```yaml
Type: String
Parameter Sets: NonCluster
Aliases: DCN

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DestinationRGName
Specifies the name of the destination replication group for which this cmdlet gets partnerships.

```yaml
Type: String
Parameter Sets: NonCluster
Aliases: DGN

Required: False
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the name of a partnership that this cmdlet gets.

```yaml
Type: String
Parameter Sets: FromGroup
Aliases: N

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SourceComputerName
Specifies a single replica source host computer NetBIOS name or FQDN for which this cmdlet gets partnerships.
The default value is the local computer.

```yaml
Type: String
Parameter Sets: NonCluster
Aliases: SCN

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -SourceRGName
Specifies the name of the source replication group for which this cmdlet gets partnerships.

```yaml
Type: String
Parameter Sets: NonCluster
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

### replicationgroups

## NOTES

## RELATED LINKS

[New-SRPartnership](./New-SRPartnership.md)

[Remove-SRPartnership](./Remove-SRPartnership.md)

[Set-SRPartnership](./Set-SRPartnership.md)

