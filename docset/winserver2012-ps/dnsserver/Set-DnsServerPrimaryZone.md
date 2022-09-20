---
external help file: DnsServer_Cmdlets.xml
Module Name: DnsServer
online version: https://learn.microsoft.com/powershell/module/dnsserver/set-dnsserverprimaryzone?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-DnsServerPrimaryZone

## SYNOPSIS
Changes settings for a DNS primary zone.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Set-DnsServerPrimaryZone [-Name] <String> [-AllowedDcForNsRecordsAutoCreation <String[]>] [-AsJob]
 [-CimSession <CimSession[]>] [-ComputerName <String>] [-DynamicUpdate <String>] [-Notify <String>]
 [-NotifyServers <IPAddress[]>] [-PassThru] [-SecondaryServers <IPAddress[]>] [-SecureSecondaries <String>]
 [-ThrottleLimit <Int32>] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Set-DnsServerPrimaryZone [-Name] <String> [-AsJob] [-CimSession <CimSession[]>] [-ComputerName <String>]
 [-DirectoryPartitionName <String>] [-PassThru] [-ThrottleLimit <Int32>] -ReplicationScope <String> [-Confirm]
 [-WhatIf]
```

### UNNAMED_PARAMETER_SET_3
```
Set-DnsServerPrimaryZone [-Name] <String> [-AsJob] [-CimSession <CimSession[]>] [-ComputerName <String>]
 [-PassThru] [-ThrottleLimit <Int32>] -ZoneFile <String> [-Confirm] [-WhatIf]
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
The example uses the **PassThru** parameter to return output.

### Example 2: Change the replication scope
```
PS C:\>Set-DnsServerPrimaryZone -Name "western.contoso.com" -ReplicationScope "Forest" -PassThru
ZoneName                            ZoneType        IsAutoCreated   IsDsIntegrated  IsReverseLookupZone  IsSigned

--------                            --------        -------------   --------------  -------------------  --------

western.contoso.com                 Primary         False           True            False                False
```

This command changes the replication scope of the zone named western.contoso.com.
The example uses the **PassThru** parameter to return output.

### Example 3: Change the path name for the zone filename
```
PS C:\>Set-DnsServerPrimaryZone -Name "western.contoso.com" -ZoneFile "tet23.dns" -PassThru
ZoneName                            ZoneType        IsAutoCreated   IsDsIntegrated  IsReverseLookupZone  IsSigned

--------                            --------        -------------   --------------  -------------------  --------

western.contoso.com                 Primary         False           False           False                False
```

This command changes the file name for the zone file for the zone western.contoso.com.
The example uses the **PassThru** parameter to return output.

## PARAMETERS

### -AllowedDcForNsRecordsAutoCreation
Specifies IP addresses of domain controllers that add their names in Name Server (NS) resource records for the zone.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

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
Parameter Sets: UNNAMED_PARAMETER_SET_2
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

### -Notify
Specifies how a DNS master server notifies secondary servers of changes to resource records.
The acceptable values for this parameter are:

- NoNotify.
The zone does not send change notifications to secondary servers.
- Notify.
The zone sends change notifications to all secondary servers.
- NotifyServers.
The zone sends change notifications to some secondary servers.
If you choose this option, specify the list of secondary servers in the **NotifyServers** parameter.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NotifyServers
Specifies an array of IP addresses of secondary DNS servers that the DNS master server notifies of changes to resource records.
You need this parameter only if you selected the value NotifyServers for the **Notify** parameter.

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

### -SecondaryServers
Specifies an array of IP addresses of DNS servers that are allowed to receive this zone through zone transfers.

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
Parameter Sets: UNNAMED_PARAMETER_SET_1
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

### -ZoneFile
Specifies the name of a  the zone file.
This parameter is relevant only for file-backed DNS.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_3
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

### Microsoft.Management.Infrastructure.CimInstance#DnsServerPrimaryZone

## NOTES

## RELATED LINKS

[Add-DnsServerPrimaryZone](./Add-DnsServerPrimaryZone.md)

[ConvertTo-DnsServerPrimaryZone](./ConvertTo-DnsServerPrimaryZone.md)

[Restore-DnsServerPrimaryZone](./Restore-DnsServerPrimaryZone.md)

