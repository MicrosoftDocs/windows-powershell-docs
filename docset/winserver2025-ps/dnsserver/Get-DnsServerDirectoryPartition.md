---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_DnsServerDirectoryPartition_v1.0.0.cdxml-help.xml
Module Name: DnsServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dnsserver/get-dnsserverdirectorypartition?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-DnsServerDirectoryPartition
---

# Get-DnsServerDirectoryPartition

## SYNOPSIS
Gets a DNS application directory partition.

## SYNTAX

### Custom (Default)
```
Get-DnsServerDirectoryPartition [-ComputerName <String>] [-Custom] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### Name
```
Get-DnsServerDirectoryPartition [-ComputerName <String>] [-Name] <String> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-DnsServerDirectoryPartition** cmdlet gets one or more Domain Name System (DNS) application server directory partitions on a DNS server.

## EXAMPLES

### Example 1: Get all DNS application directory partitions
```
PS C:\> Get-DnsServerDirectoryPartition

server.DirectoryPartitionName        State                         Flags                         ZoneCount
-----------------------------        -----                         -----                         ---------
DomainDnsZones.mytest.cont...        0(DNS_DP_OKAY)                Enlisted Auto Domain          3
ForestDnsZones.mytest.cont...        0(DNS_DP_OKAY)                Enlisted Auto Forest          2
```

This command gets all the DNS application directory partitions on the local computer.

### Example 2: Get all custom application directory partitions
```
PS C:\> Get-DnsServerDirectoryPartition -Custom

DirectoryPartitionName        State                         Flags                         ZoneCount
----------------------        -----                         -----                         ---------
DomainDnsZones.mytest.cont... 0(DNS_DP_OKAY)                Enlisted Auto Domain          3
```

This command gets all the custom application directory partitions on the local computer.

### Example 3: Get an application directory partition by using name
```
PS C:\> Get-DnsServerDirectoryPartition -Name "DomainDnsZones.dept.contoso.com"
```

This command gets the DNS application directory partition named DomainDnsZones.dept.contoso.com on the local computer.

## PARAMETERS

### -AsJob
Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to complete.

The cmdlet immediately returns an object that represents the job and then displays the command prompt.
You can continue to work in the session while the job completes.
To manage the job, use the `*-Job` cmdlets.
To get the job results, use the [Receive-Job](https://go.microsoft.com/fwlink/?LinkID=113372) cmdlet.

For more information about Windows PowerShell background jobs, see [about_Jobs](https://go.microsoft.com/fwlink/?LinkID=113251).

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
Specifies a remote DNS server.
You can specify an IP address or any value that resolves to an IP address, such as a fully qualified domain name (FQDN), host name, or NETBIOS name.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Cn

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Custom
Indicates that this cmdlet returns custom directory partitions.

```yaml
Type: SwitchParameter
Parameter Sets: Custom
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the FQDN of a DNS application directory partition.

```yaml
Type: String
Parameter Sets: Name
Aliases: DirectoryPartitionName

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

### Microsoft.Management.Infrastructure.CimInstance#DnsServerDirectoryPartition

## NOTES

## RELATED LINKS

[Add-DnsServerDirectoryPartition](./Add-DnsServerDirectoryPartition.md)

[Register-DnsServerDirectoryPartition](./Register-DnsServerDirectoryPartition.md)

[Unregister-DnsServerDirectoryPartition](./Unregister-DnsServerDirectoryPartition.md)

[Remove-DnsServerDirectoryPartition](./Remove-DnsServerDirectoryPartition.md)

