---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_DnsServerPrimaryZone_v1.0.0.cdxml-help.xml
Module Name: DnsServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dnsserver/convertto-dnsserverprimaryzone?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertTo-DnsServerPrimaryZone
---

# ConvertTo-DnsServerPrimaryZone

## SYNOPSIS
Converts a zone to a DNS primary zone.

## SYNTAX

### ADZone (Default)
```
ConvertTo-DnsServerPrimaryZone [-ComputerName <String>] [-Name] <String> [-LoadExisting] [-PassThru] [-Force]
 [-ReplicationScope] <String> [[-DirectoryPartitionName] <String>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### FileZone
```
ConvertTo-DnsServerPrimaryZone [-ComputerName <String>] [-Name] <String> [-LoadExisting] [-PassThru] [-Force]
 -ZoneFile <String> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **ConvertTo-DnsServerPrimaryZone** cmdlet converts a Domain Name System (DNS) zone to a DNS primary zone.
Use this cmdlet to promote a secondary zone to a primary zone on the server.
For a file-backed zone, ensure there is only one server that hosts the primary zone.

## EXAMPLES

### Example 1: Convert a file-backed zone
```
PS C:\> ConvertTo-DnsServerPrimaryZone -Name "west03.contoso.com" -PassThru -Verbose -ZoneFile "west03.contoso.com" -Force

VERBOSE: Convert west03.contoso.com zone to (file backed/AD integrated) DNS primary zone on DNS-11 server.
ZoneName                            ZoneType        IsAutoCreated   IsDsIntegrated  IsReverseLookupZone  IsSigned
--------                            --------        -------------   --------------  -------------------  --------
west03.contoso.com                  Primary         False           False           False                False
```

This command converts zone named west03.contoso.com to a file-backed primary zone on the current server.
This example uses the *Force* parameter to skip a confirmation message.

### Example 2: Convert an Active Directory-integrated zone
```
PS C:\> ConvertTo-DnsServerPrimaryZone "west04.contoso.com" -PassThru -Verbose -ReplicationScope Domain -Force
```

This command converts a zone named west04.contoso.com to an Active Directory-integrated primary zone.
The zone will be replicated to all DNS servers in the domain.
This example uses the *Force* parameter to skip a confirmation message.

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
Specifies a DNS server.
If you do not specify this parameter, the command runs on the local system.
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

### -DirectoryPartitionName
Specifies a directory partition on which to store the zone.
Use this parameter when the *ReplicationScope* parameter has a value of Custom.

```yaml
Type: String
Parameter Sets: ADZone
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Force
Converts a zone without prompting you for confirmation.
By default, the cmdlet prompts you for confirmation before it proceeds.

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

### -LoadExisting
Indicates that the DNS server loads an existing file for the zone.
If you do not specify this parameter, this cmdlet creates default zone records.
This parameter is relevant only for file-backed zones.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the name of a zone.

```yaml
Type: String
Parameter Sets: (All)
Aliases: ZoneName

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

### -ReplicationScope
Specifies a partition on which to store an Active Directory-integrated zone.
The acceptable values for this parameter are:

- Custom.
Any custom directory partition that a user creates.
Specify a custom directory partition by using the *DirectoryPartitionName* parameter.
- Domain.
The domain directory partition.
- Forest.
The ForestDnsZone directory partition.
- Legacy.
A legacy directory partition.

```yaml
Type: String
Parameter Sets: ADZone
Aliases:
Accepted values: Forest, Domain, Legacy, Custom

Required: True
Position: 2
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

### -ZoneFile
Specifies the name of the zone file.
This parameter is only relevant for file-backed DNS.

```yaml
Type: String
Parameter Sets: FileZone
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#DnsServerPrimaryZone

## NOTES

## RELATED LINKS

[Add-DnsServerPrimaryZone](./Add-DnsServerPrimaryZone.md)

[Restore-DnsServerPrimaryZone](./Restore-DnsServerPrimaryZone.md)

[Set-DnsServerPrimaryZone](./Set-DnsServerPrimaryZone.md)

