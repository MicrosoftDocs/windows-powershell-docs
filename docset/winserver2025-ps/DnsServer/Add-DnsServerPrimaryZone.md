---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_DnsServerPrimaryZone_v1.0.0.cdxml-help.xml
Module Name: DnsServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dnsserver/add-dnsserverprimaryzone?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-DnsServerPrimaryZone
---

# Add-DnsServerPrimaryZone

## SYNOPSIS
Adds a primary zone to a DNS server.

## SYNTAX

### ADForwardLookupZone (Default)
```
Add-DnsServerPrimaryZone [-ResponsiblePerson <String>] [-DynamicUpdate <String>] [-LoadExisting]
 [-ComputerName <String>] [-PassThru] [-Name] <String> [-ReplicationScope] <String>
 [[-DirectoryPartitionName] <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### FileReverseLookupZone
```
Add-DnsServerPrimaryZone [-ResponsiblePerson <String>] [-DynamicUpdate <String>] [-LoadExisting]
 [-ComputerName <String>] [-PassThru] -NetworkId <String> -ZoneFile <String> [-VirtualizationInstance <String>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### FileForwardLookupZone
```
Add-DnsServerPrimaryZone [-ResponsiblePerson <String>] [-DynamicUpdate <String>] [-LoadExisting]
 [-ComputerName <String>] [-PassThru] [-Name] <String> -ZoneFile <String> [-VirtualizationInstance <String>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ADReverseLookupZone
```
Add-DnsServerPrimaryZone [-ResponsiblePerson <String>] [-DynamicUpdate <String>] [-LoadExisting]
 [-ComputerName <String>] [-PassThru] [-ReplicationScope] <String> [[-DirectoryPartitionName] <String>]
 -NetworkId <String> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Add-DnsServerPrimaryZone** cmdlet adds a specified primary zone on a Domain Name System (DNS) server.

You can add an Active Directory-integrated forward lookup zone, an Active Directory-integrated reverse lookup zone, a file-backed forward lookup zone, or a file-backed reverse lookup zone.

## EXAMPLES

### Example 1: Create a primary zone
```
PS C:\> Add-DnsServerPrimaryZone -Name "west01.contoso.com" -ReplicationScope "Forest" -PassThru
```

This command creates an Active Directory-integrated forward lookup zone called west01.contoso.com with Forest-wide replication scope.

### Example 2: Create a file-backed primary zone
```
PS C:\> Add-DnsServerPrimaryZone -Name "west02.contoso.com" -ZoneFile "west02.contoso.com.dns"
```

This command creates a file-backed primary forward lookup zone called west02.contoso.com with the specified DNS file.

### Example 3: Create a reverse lookup zone
```
PS C:\> Add-DnsServerPrimaryZone -NetworkID "10.1.0.0/24" -ReplicationScope "Forest"

ZoneName                            ZoneType        IsAutoCreated   IsDsIntegrated  IsReverseLookupZone  IsSigned
--------                            --------        -------------   --------------  -------------------  --------
1.10.in-addr.arpa                   Primary         False           True            True                 False
```

This command creates the Active Directory-integrated class C reverse lookup zone 0.1.10.in-addr.arpa with Forest-wide replication scope.

### Example 4: Create a file-backed reverse lookup zone
```
PS C:\> Add-DnsServerPrimaryZone -NetworkID 10.3.0.0/24 -ZoneFile "0.3.10.in-addr.arpa.dns"
```

This command creates the file-backed reverse lookup zone 0.3.10.in-addr.arpa.

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
Parameter Sets: ADForwardLookupZone
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: ADReverseLookupZone
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DynamicUpdate
Specifies how a zone accepts dynamic updates.
The acceptable values for this parameter are:

- None
- Secure
- NonsecureAndSecure

Secure DNS updates are available only for Active Directory-integrated zones.

```yaml
Type: String
Parameter Sets: (All)
Aliases:
Accepted values: None, Secure, NonsecureAndSecure

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -LoadExisting
Indicates that the server loads an existing file for the zone.
Otherwise, the cmdlet creates default zone records automatically.
This switch is relevant only for file-backed zones.

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
Specifies a name for the zone the cmdlet creates.

```yaml
Type: String
Parameter Sets: ADForwardLookupZone, FileForwardLookupZone
Aliases: ZoneName

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NetworkId
Specifies a network ID and prefix length for a reverse lookup zone.
Use the format A.B.C.D/prefix for IPv4 or 1111:2222:3333:4444::/prefix for IPv6.

For IPv4, the cmdlet creates only class A, B, C, or D reverse lookup zones.
If you specify a prefix that is between classes, the cmdlet uses the longer prefix that is divisible by 8.
For example, a value of 10.2.10.0/23 adds the 10.2.10.0/24 reverse lookup zone, and the 10.2.11.0/24 reverse lookup zone is not created.
If you enter an IPv4 prefix longer than /24, the cmdlet creates a /32 reverse lookup zone.

For IPv6, the cmdlet creates ip6.arpa zones for prefixes from /16 to /128 that are divisible by 4.
If you specify a prefix that is between values, the cmdlet uses the longer prefix that is divisible by 4.
For example, entering a value of AAAA::/58 adds the AAAA::/60  ip6.arpa zone.
If you do not enter a prefix, the cmdlet uses a default prefix value of /128.

```yaml
Type: String
Parameter Sets: FileReverseLookupZone, ADReverseLookupZone
Aliases:

Required: True
Position: Named
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
Parameter Sets: ADForwardLookupZone, ADReverseLookupZone
Aliases:
Accepted values: Forest, Domain, Legacy, Custom

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResponsiblePerson
Specifies a person responsible for the zone.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
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

### -VirtualizationInstance
Specifies the virtualization instance in which the zone will be added.
A virtualization instance is logical partition in a DNS Server, which is capable of independently hosting zones and zone scopes.
Same name zones and zone scopes can be hosted in different virtualization instances.
This parameter is optional and if not provided it will add the zone into the default virtualization instance which is functionally equivalent to a standard DNS server.

```yaml
Type: String
Parameter Sets: FileReverseLookupZone, FileForwardLookupZone
Aliases:

Required: False
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

### -ZoneFile
Specifies a name of the zone file.
This parameter is only relevant for file-backed DNS.

```yaml
Type: String
Parameter Sets: FileReverseLookupZone, FileForwardLookupZone
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

[ConvertTo-DnsServerPrimaryZone](./ConvertTo-DnsServerPrimaryZone.md)

[Restore-DnsServerPrimaryZone](./Restore-DnsServerPrimaryZone.md)

[Set-DnsServerPrimaryZone](./Set-DnsServerPrimaryZone.md)

