---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_DnsServerConditionalForwarder_v1.0.0.cdxml-help.xml
Module Name: DnsServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dnsserver/add-dnsserverconditionalforwarderzone?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-DnsServerConditionalForwarderZone
---

# Add-DnsServerConditionalForwarderZone

## SYNOPSIS
Adds a conditional forwarder to a DNS server.

## SYNTAX

### FileForwardLookupZone (Default)
```
Add-DnsServerConditionalForwarderZone [-LoadExisting] [-MasterServers] <IPAddress[]> [-ComputerName <String>]
 [-UseRecursion] [[-ForwarderTimeout] <UInt32>] [-PassThru] [-Name] <String> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ADForwardLookupZone
```
Add-DnsServerConditionalForwarderZone [-LoadExisting] [-MasterServers] <IPAddress[]> [-ComputerName <String>]
 [-UseRecursion] [[-ForwarderTimeout] <UInt32>] [-PassThru] [-DirectoryPartitionName <String>]
 [-ReplicationScope <String>] [-Name] <String> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Add-DnsServerConditionalForwarderZone** cmdlet adds a conditional forwarder to a Domain Name System (DNS) server.
You can select the master servers, forwarder time-out, recursion, host computer, replication scope, and directory partition for the conditional forwarder.
Conditional forwarders are stored as zones on a DNS server.

## EXAMPLES

### Example 1: Create a non-Active Directory-integrated forwarder
```
PS C:\> Add-DnsServerConditionalForwarderZone -Name "contoso.com" -MasterServers 2001:4898:7020:f100:458f:e6a2:fcaf:698c,172.23.90.124 -PassThru

ZoneName                            ZoneType        IsAutoCreated   IsDsIntegrated  IsReverseLookupZone  IsSigned
--------                            --------        -------------   --------------  -------------------  --------
contoso.com                         Forwarder       False           False           False
```

This command creates a conditional forwarder zone called contoso.com.
The entries are stored in the registry.
The command includes IP addresses for one or more master DNS servers.
The command uses the *PassThru* parameter.

### Example 2: Create an Active Directory-integrated forwarder
```
PS C:\> Add-DnsServerConditionalForwarderZone -Name "contoso.com" -ReplicationScope "Forest" -MasterServers 2001:4898:7020:f100:458f:e6a2:fcaf:698c,172.23.90.124
```

This command creates an Active Directory-integrated conditional forwarder zone for contoso.com.
The command specifies IP addresses for one or more master DNS servers.

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
Specifies the DNS server.
The cmdlet adds the forwarder to this server.
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
Specifies a directory partition on which to store the forwarder.
Conditional forwarders are internally stored as zones.
Use this parameter when the *ReplicationScope* parameter has a value of Custom.

```yaml
Type: String
Parameter Sets: ADForwardLookupZone
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ForwarderTimeout
Specifies a length of time, in seconds, that a DNS server waits for a master server to resolve a query.
If a server does not resolve the request, the next server in the list is queried until all master servers are queried.
After this period, the DNS server can attempt to resolve the query itself.
This parameter applies only to the forwarder zone.
The minimum value is 0.
The maximum value is 15.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -LoadExisting
Indicates that the server loads existing data for the forwarder from the registry.
Conditional forwarders are internally stored as zones.
This parameter is not valid for Active Directory-integrated zones.

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

### -MasterServers
Specifies an array of IP addresses of the master servers of the zone.
DNS queries for a forwarded zone are sent to master servers.
You can use both IPv4 and IPv6 addresses.
You must specify at least one master server.

```yaml
Type: IPAddress[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the name of a zone.
The cmdlet adds a conditional forwarder for this zone.

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
Specifies the replication scope for the conditional forwarder.
Conditional forwarders are stored internally as zones.
The acceptable values for this parameter are:

- Custom.
Replicate the conditional forwarder to all DNS servers running on domain controllers enlisted in a custom directory partition.
- Domain.
Replicate the conditional forwarder to all DNS servers that run on domain controllers in the domain.
- Forest.
Replicate the conditional forwarder to all DNS servers that run on domain controllers in the forest.
- Legacy.
Replicate the conditional forwarder to all domain controllers in the domain.

```yaml
Type: String
Parameter Sets: ADForwardLookupZone
Aliases:
Accepted values: Forest, Domain, Legacy, Custom

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

### -UseRecursion
Specifies whether a DNS server attempts to resolve a query after the forwarder fails to resolve it.
A value of $False prevents a DNS server from attempting resolution using other DNS servers.
This parameter overrides the Use Recursion setting for a DNS server.

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

### Microsoft.Management.Infrastructure.CimInstance#DnsServerConditionalForwarderZone

## NOTES

## RELATED LINKS

[Set-DnsServerConditionalForwarderZone](./Set-DnsServerConditionalForwarderZone.md)

