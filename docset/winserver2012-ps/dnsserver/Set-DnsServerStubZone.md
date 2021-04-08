---
author: Kateyanne
external help file: DnsServer_Cmdlets.xml
manager: dansimp
Module Name: DnsServer
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/dnsserver/set-dnsserverstubzone?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-DnsServerStubZone

## SYNOPSIS
Changes settings for a DNS server stub zone.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Set-DnsServerStubZone [-Name] <String> [-AsJob] [-CimSession <CimSession[]>] [-ComputerName <String>]
 [-LocalMasters <IPAddress[]>] [-MasterServers <IPAddress[]>] [-PassThru] [-ThrottleLimit <Int32>] [-Confirm]
 [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Set-DnsServerStubZone [-Name] <String> [-AsJob] [-CimSession <CimSession[]>] [-ComputerName <String>]
 [-DirectoryPartitionName <String>] [-PassThru] [-ThrottleLimit <Int32>] -ReplicationScope <String> [-Confirm]
 [-WhatIf]
```

## DESCRIPTION
The **Set-DnsServerStubZone** cmdlet changes settings for an existing stub zone.
A stub zone is a copy of a Domain Name System (DNS) zone that contains only resource records that identify the authoritative DNS servers for that zone.

The stub zone can be a forward lookup zone or a reverse lookup zone.
The stub zone can be an Active Directory-integrated zone or a file-backed zone.

## EXAMPLES

### Example 1: Change master servers for a stub zone
```
PS C:\> Set-DnsServerStubZone -Name "west03.contoso.com" -MasterServers 172.23.90.124,2001:4898:7020:f100:458f:e6a2:fcaf:698c
```

This command changes the master servers for a stub zone named west03.contoso.com.

### Example 2: Change replication scope for a stub zone
```
PS C:\>Set-DnsServerStubZone  -Name "west04.contoso.com" -ReplicationScope "Domain" -PassThru
ZoneName                            ZoneType        IsAutoCreated   IsDsIntegrated  IsReverseLookupZone  IsSigned

--------                            --------        -------------   --------------  -------------------  --------

west04.contoso.com                  Stub            False           True            False
```

This command changes the replication scope for a stub zone named west04.contoso.com to all DNS servers in the domain.

## PARAMETERS

### -AsJob
ps_cimcommon_asjob

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
Enter a computer name or a session object, such as the output of a New-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227967 or Get-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227966 cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName
Specifies a DNS server.
If you do not specify this parameter, the command runs on the local system.
You can specify an IP address or any value that resolves to an IP address, such as a fully qualified domain name (FQDN), Hostname, or NETBIOS name.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DirectoryPartitionName
Specifies a directory partition on which to store the zone.
Use this parameter when the **ReplicationScope** parameter has a value of Custom.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -LocalMasters
Specifies list of master DNS servers stored in the Windows Registry on the local server.
If it exists, this list overrides the list of master servers stored in Active Directory.

```yaml
Type: IPAddress[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MasterServers
Specifies an array of IP addresses of the master servers of the zone.
You can use both IPv4 and IPv6.

The DNS server stores this list in the Windows Registry of the local server.
If it exists, this list overrides the list of master servers stored in Active Directory.

```yaml
Type: IPAddress[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the name of a zone.
The cmdlet modifies settings for this zone.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
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
Specify a custom directory partition by using the **DirectoryPartitionName** parameter.
- Domain.
The domain directory partition. 
- Forest.
The ForestDnsZone directory partition.
- Legacy.
A legacy directory partition.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
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

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#DnsServerStubZone

## NOTES

## RELATED LINKS

[Add-DnsServerStubZone](./Add-DnsServerStubZone.md)

