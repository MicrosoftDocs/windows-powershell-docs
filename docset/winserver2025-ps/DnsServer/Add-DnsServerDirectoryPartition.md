---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_DnsServerDirectoryPartition_v1.0.0.cdxml-help.xml
Module Name: DnsServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dnsserver/add-dnsserverdirectorypartition?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-DnsServerDirectoryPartition
---

# Add-DnsServerDirectoryPartition

## SYNOPSIS
Creates a DNS application directory partition.

## SYNTAX

### Name (Default)
```
Add-DnsServerDirectoryPartition [-ComputerName <String>] [-PassThru] [-Name] <String>
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### BuiltIn
```
Add-DnsServerDirectoryPartition [-ComputerName <String>] [-PassThru] -Type <String>
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Add-DnsServerDirectoryPartition** cmdlet creates a Domain Name System (DNS) application directory partition.
After you install a DNS server, DNS creates an application directory partition for the service at the forest and domain levels.
This cmdlet creates additional DNS application directory partitions.

You can store DNS zones in the domain or application directory partitions of Active Directory Domain Services (AD DS).
A partition is a data structure in AD DS that distinguishes data for different replication purposes.
When you create an application directory partition for DNS, you can control the scope of replication for the zone that is stored in that partition.

## EXAMPLES

### Example 1: Create a DNS application directory partition
```
PS C:\> Add-DnsServerDirectoryPartition -Name "ADpart"
```

This command adds a new DNS application directory partition named ADpart to the local computer.

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

### -Name
Specifies a name for the new DNS application directory partition.

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

### -PassThru
Returns an object representing the item with which you are working.
By default, this cmdlet does not generate any output.

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

### -Type
Specifies a type of DNS application directory partition.
The acceptable values for this parameter are:

- /Domain
- /Forest
- /AllDomains

To create a default domain-wide DNS application directory partition for the Active Directory domain where the specified DNS server is located, specify /Domain.

To create a default forest-wide DNS application directory partition for the Active Directory forest where the specified DNS server is located, specify /Forest.

The *ComputerName* parameter is ignored for an /AllDomains DNS application directory partition.
The computer from where you run this command must be joined to a domain in the forest where you want to create all of the default domain-wide application directory partitions.

```yaml
Type: String
Parameter Sets: BuiltIn
Aliases:
Accepted values: Forest, Domain

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#DnsServerDirectoryPartition

## NOTES

## RELATED LINKS

[Get-DnsServerDirectoryPartition](./Get-DnsServerDirectoryPartition.md)

[Register-DnsServerDirectoryPartition](./Register-DnsServerDirectoryPartition.md)

[Unregister-DnsServerDirectoryPartition](./Unregister-DnsServerDirectoryPartition.md)

[Remove-DnsServerDirectoryPartition](./Remove-DnsServerDirectoryPartition.md)

