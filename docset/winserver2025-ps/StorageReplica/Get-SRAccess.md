---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_WvrAdminTasks.cdxml-help.xml
Module Name: StorageReplica
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/storagereplica/get-sraccess?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-SRAccess
---

# Get-SRAccess

## SYNOPSIS
Gets security access between failover clusters.

## SYNTAX

```
Get-SRAccess [[-ComputerName] <String>] [[-Cluster] <String>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SRAccess** cmdlet gets the security access required between failover clusters to replicate by using Storage Replica.
You do not have to use this cmdlet for stretch clusters or server-to-server replication.

## EXAMPLES

### Example 1: Display clusters that have paired security access
```
PS C:\>Get-SRAccess
ClusterName PairedClusterName PSComputerName
----------- ----------------- --------------
            sr-srvclusb
```

This command displays the clusters that have paired security access to the current cluster.

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

### -Cluster
Specifies a partner failover cluster NetBIOS name or fully qualified domain name (FQDN) of a cluster for which this cmdlet gets information.

```yaml
Type: String
Parameter Sets: (All)
Aliases: N

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ComputerName
Specifies a single replica host computer NetBIOS name or FQDN of a computer for which this cmdlet gets information.
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

[Grant-SRAccess](./Grant-SRAccess.md)

[Revoke-SRAccess](./Revoke-SRAccess.md)

