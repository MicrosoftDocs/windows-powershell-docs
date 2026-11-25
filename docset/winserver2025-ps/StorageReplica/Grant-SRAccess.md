---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_WvrAdminTasks.cdxml-help.xml
Module Name: StorageReplica
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/storagereplica/grant-sraccess?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Grant-SRAccess
---

# Grant-SRAccess

## SYNOPSIS
Grants security access between failover clusters to enable replication.

## SYNTAX

```
Grant-SRAccess [[-ComputerName] <String>] [-Cluster] <String> [-Force] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Grant-SRAccess** cmdlet grants security access between failover clusters to enable replication by using Storage Replica.
You do not have to use this cmdlet for stretch clusters or server-to-server replication.

## EXAMPLES

### Example 1: Grant access to a cluster
```
PS C:\>Grant-SRAccess -ComputerName "SR-SRV01" -Cluster "SR-SRVCLUSB"
PS C:\> Grant-SRAccess -ComputerName "SR-SRV03" -Cluster "SR-SRVCLUSA"
```

The first command grants a node named SR-SRV01 in the SR-SRVCLUSA cluster access to the SR-SRVCLUSB cluster.
You can specify any node in a cluster for the *ComputerName* parameter.
The command updates the access control list for the entire cluster.

The second command grants a node named SR-SRV03 in the SR-SRVCLUSB cluster access to the SR-SRVCLUSA cluster.

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
Specifies a partner failover cluster NetBIOS name or fully qualified domain name (FQDN) of a cluster.
This cmdlet adds this cluster to the Storage Replica access control list on the local cluster to enable replication.
You must run this cmdlet for both clusters before you create a partnership.

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

### -ComputerName
Specifies a single replica host computer NetBIOS name or FQDN on which this cmdlet grants access.
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

[Get-SRAccess](./Get-SRAccess.md)

[Revoke-SRAccess](./Revoke-SRAccess.md)

