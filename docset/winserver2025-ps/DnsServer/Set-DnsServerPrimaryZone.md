---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_DnsServerPrimaryZone_v1.0.0.cdxml-help.xml
Module Name: DnsServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dnsserver/set-dnsserverprimaryzone?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-DnsServerPrimaryZone
---

# Set-DnsServerPrimaryZone

## SYNOPSIS
Changes settings for a DNS primary zone.

## SYNTAX

### Parameters (Default)
```
Set-DnsServerPrimaryZone [-Name] <String> [-ComputerName <String>] [-PassThru]
 [-AllowedDcForNsRecordsAutoCreation <String[]>] [-DynamicUpdate <String>] [-Notify <String>]
 [-NotifyServers <IPAddress[]>] [-SecondaryServers <IPAddress[]>] [-SecureSecondaries <String>]
 [-IgnorePolicies <Boolean>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### FileZone
```
Set-DnsServerPrimaryZone [-Name] <String> [-ComputerName <String>] [-PassThru] -ZoneFile <String>
 [-VirtualizationInstance <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### ADZone
```
Set-DnsServerPrimaryZone [-Name] <String> [-ComputerName <String>] [-PassThru] -ReplicationScope <String>
 [-DirectoryPartitionName <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-DnsServerPrimaryZone** cmdlet changes settings for an existing Domain Name System (DNS) primary zone.
You can change values that are relevant for either Active Directory-integrated zones or file-backed zones.

## EXAMPLES

### Example 1: Change the dynamic update setting
```
PS C:\> Set-DnsServerPrimaryZone -Name "western.contoso.com" -DynamicUpdate "NonsecureAndSecure" -PassThru

ZoneName                            ZoneType        IsAutoCreated   IsDsIntegrated  IsReverseLookupZone  IsSigned
--------                            --------        -------------   --------------  -------------------  --------
western.contoso.com                 Primary         False           True            False                False
```

This command changes the dynamic update setting to NonsecureAndSecure for the zone named western.contoso.com.
The example uses the *PassThru* parameter to return output.

### Example 2: Change the replication scope
```
PS C:\> Set-DnsServerPrimaryZone -Name "western.contoso.com" -ReplicationScope "Forest" -PassThru

ZoneName                            ZoneType        IsAutoCreated   IsDsIntegrated  IsReverseLookupZone  IsSigned
--------                            --------        -------------   --------------  -------------------  --------
western.contoso.com                 Primary         False           True            False                False
```

This command changes the replication scope of the zone named western.contoso.com.
The example uses the *PassThru* parameter to return output.

### Example 3: Change the name for the zone file
```
PS C:\> Set-DnsServerPrimaryZone -Name "western.contoso.com" -ZoneFile "tet23.dns" -PassThru

ZoneName                            ZoneType        IsAutoCreated   IsDsIntegrated  IsReverseLookupZone  IsSigned
--------                            --------        -------------   --------------  -------------------  --------
western.contoso.com                 Primary         False           False           False                False
```

This command changes the file name for the zone file for the zone western.contoso.com.
The example uses the *PassThru* parameter to return output.

## PARAMETERS

### -AllowedDcForNsRecordsAutoCreation
Specifies IP addresses of domain controllers that add their names in Name Server (NS) resource records for the zone.

```yaml
Type: String[]
Parameter Sets: Parameters
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

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
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DynamicUpdate
Specifies how a zone accepts dynamic updates.
Servers that accept dynamic updates can receive client registration requests.
The acceptable values for this parameter are:

- None
- Secure
- NonsecureAndSecure

DNS update security is available only for Active Directory-integrated zones.

```yaml
Type: String
Parameter Sets: Parameters
Aliases:
Accepted values: None, Secure, NonsecureAndSecure

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IgnorePolicies
Indicates whether to ignore policies for this zone.

```yaml
Type: Boolean
Parameter Sets: Parameters
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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

### -Notify
Specifies how a DNS master server notifies secondary servers of changes to resource records.
The acceptable values for this parameter are:

- NoNotify.
The zone does not send change notifications to secondary servers.
- Notify.
The zone sends change notifications to all secondary servers.
- NotifyServers.
The zone sends change notifications to some secondary servers.
If you choose this option, specify the list of secondary servers in the *NotifyServers* parameter.

```yaml
Type: String
Parameter Sets: Parameters
Aliases:
Accepted values: NoNotify, Notify, NotifyServers

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NotifyServers
Specifies an array of IP addresses of secondary DNS servers that the DNS master server notifies of changes to resource records.
You need this parameter only if you selected the value NotifyServers for the *Notify* parameter.

```yaml
Type: IPAddress[]
Parameter Sets: Parameters
Aliases:

Required: False
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
Parameter Sets: ADZone
Aliases:
Accepted values: Forest, Domain, Legacy, Custom

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SecondaryServers
Specifies an array of IP addresses of DNS servers that are allowed to receive this zone through zone transfers.

```yaml
Type: IPAddress[]
Parameter Sets: Parameters
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SecureSecondaries
Specifies how a DNS master server allows zone transfers to secondary servers.
You can configure the DNS server to send zone transfers only certain servers.
If other servers request zone transfers, the DNS server rejects the requests.

The acceptable values for this parameter are:

- NoTransfer.
Zone transfers are not allowed on this DNS server for this zone.
- TransferAnyServer.
Zone transfers are allowed to any DNS server.
- TransferToZoneNameServer.
Zone transfers are allowed only to servers in the name servers (NS) records for this zone.
- TransferToSecureServers.
Zone transfers are allowed only for secondary servers.

```yaml
Type: String
Parameter Sets: Parameters
Aliases:
Accepted values: NoTransfer, TransferAnyServer, TransferToZoneNameServer, TransferToSecureServers

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
Parameter Sets: FileZone
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
Specifies the name of the zone file.
This parameter is relevant only for file-backed DNS.

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

[ConvertTo-DnsServerPrimaryZone](./ConvertTo-DnsServerPrimaryZone.md)

[Restore-DnsServerPrimaryZone](./Restore-DnsServerPrimaryZone.md)

