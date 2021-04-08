---
author: Kateyanne
external help file: DnsServer_Cmdlets.xml
manager: dansimp
Module Name: DnsServer
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/dnsserver/add-dnsserverstubzone?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Add-DnsServerStubZone

## SYNOPSIS
Adds a DNS stub zone.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Add-DnsServerStubZone [-Name] <String> [-MasterServers] <IPAddress[]> [-ReplicationScope] <String>
 [[-DirectoryPartitionName] <String>] [-AsJob] [-CimSession <CimSession[]>] [-ComputerName <String>]
 [-LoadExisting] [-PassThru] [-ThrottleLimit <Int32>] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Add-DnsServerStubZone [-MasterServers] <IPAddress[]> [-AsJob] [-CimSession <CimSession[]>]
 [-ComputerName <String>] [-LoadExisting] [-PassThru] [-ThrottleLimit <Int32>] -NetworkId <String>
 -ZoneFile <String> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_3
```
Add-DnsServerStubZone [-Name] <String> [-MasterServers] <IPAddress[]> [-AsJob] [-CimSession <CimSession[]>]
 [-ComputerName <String>] [-LoadExisting] [-PassThru] [-ThrottleLimit <Int32>] -ZoneFile <String> [-Confirm]
 [-WhatIf]
```

### UNNAMED_PARAMETER_SET_4
```
Add-DnsServerStubZone [-MasterServers] <IPAddress[]> [-ReplicationScope] <String>
 [[-DirectoryPartitionName] <String>] [-AsJob] [-CimSession <CimSession[]>] [-ComputerName <String>]
 [-LoadExisting] [-PassThru] [-ThrottleLimit <Int32>] -NetworkId <String> [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Add-DnsServerStubZone** cmdlet adds a stub zone.
A stub zone is a copy of a Domain Name System (DNS) zone that contains only resource records that identify the DNS servers for that zone.

You can add either a forward lookup zone or a reverse lookup zone.
You can add either an Active Directory-integrated zone or a file-backed zone.

## EXAMPLES

### Example 1: Add a file-backed stub zone
```
PS C:\> Add-DnsServerStubZone -Name "west02.contoso.com" -MasterServers "172.23.90.124" -PassThru -ZoneFile "west02_contoso.dns"
```

This command adds west02.contoso.com as a file-backed stub zone.
The command specifies a master server and uses the **PassThru** parameter to produce output.

### Example 2: Add an Active Directory-integrated stub zone
```
PS C:\>Add-DnsServerStubZone -Name "west03.contoso.com" -MasterServers 172.23.90.124 -PassThru -ReplicationScope "Forest"
```

This command adds west03.contoso.com as a stub zone replicated to all DNS servers in the forest.

### Example 3: Add an Active Directory-integrated reverse lookup zone
```
PS C:\>Add-DnsServerStubZone -NetworkId 10.1.2.0/24 -MasterServers 172.23.90.124 -PassThru -ReplicationScope Forest
```

This command adds a stub zone for the network 2.1.10.in-addr.arpa, which is replicated to all DNS servers in the forest.

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
You can specify an IP address or any value that resolves to an IP address, such as a fully qualified domain name (FQDN), host name, or NETBIOS name.

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
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_4
Aliases: 

Required: False
Position: 5
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -LoadExisting
Loads an existing file for the zone.
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

### -MasterServers
Specifies an array of IP addresses of the master servers of the zone.
You can use both IPv4 and IPv6.

```yaml
Type: IPAddress[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies a name of a zone.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_3
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NetworkId
Specifies a network ID and prefix length for a reverse lookup zone.
Use the format A.B.C.D/prefix.

The cmdlet creates only class A, B, C, or D zones.
If you specify a prefix that is between classes, the cmdlet uses the longer prefix divisible by 8.
For example, a value of 10.2.10.0/23 results in the 10.2.10.0/24 reverse lookup zone, not the 10.2.11.0/24 reverse lookup zone.
If you enter a prefix longer than /24, the cmdlet creates a /32 reverse lookup zone.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2, UNNAMED_PARAMETER_SET_4
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
Specify a custom directory partition by using the **DirectoryPartitionName** parameter.
- Domain.
The domain directory partition. 
- Forest.
The ForestDnsZone directory partition.
- Legacy.
A legacy directory partition.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_4
Aliases: 

Required: True
Position: 4
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

### -ZoneFile
Specifies a name of the zone file.
This parameter is only relevant for file-backed DNS.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2, UNNAMED_PARAMETER_SET_3
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

[Set-DnsServerStubZone](./Set-DnsServerStubZone.md)

