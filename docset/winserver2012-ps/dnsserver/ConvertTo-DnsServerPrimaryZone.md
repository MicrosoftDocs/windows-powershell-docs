---
external help file: DnsServer_Cmdlets.xml
Module Name: DnsServer
online version: https://learn.microsoft.com/powershell/module/dnsserver/convertto-dnsserverprimaryzone?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# ConvertTo-DnsServerPrimaryZone

## SYNOPSIS
Converts a zone to a DNS primary zone.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
ConvertTo-DnsServerPrimaryZone [-Name] <String> [-ReplicationScope] <String>
 [[-DirectoryPartitionName] <String>] [-AsJob] [-CimSession <CimSession[]>] [-ComputerName <String>] [-Force]
 [-LoadExisting] [-PassThru] [-ThrottleLimit <Int32>] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
ConvertTo-DnsServerPrimaryZone [-Name] <String> [-AsJob] [-CimSession <CimSession[]>] [-ComputerName <String>]
 [-Force] [-LoadExisting] [-PassThru] [-ThrottleLimit <Int32>] -ZoneFile <String> [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **ConvertTo-DnsServerPrimaryZone** converts a Domain Name System (DNS) zone to a DNS primary zone.
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
This example uses the **Force** parameter to skip a confirmation message.

### Example 2: Convert an Active Directory-integrated zone
```
PS C:\>ConvertTo-DnsServerPrimaryZone "west04.contoso.com" -PassThru -Verbose -ReplicationScope Domain -Force
```

This command converts a zone named west04.contoso.com to an Active Directory-integrated primary zone.
The zone will be replicated to all DNS servers in the domain.
This example uses the **Force** parameter to skip a confirmation message.

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
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: 4
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
Loads an existing file for the zone.
Otherwise, the cmdlet creates default zone records.
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
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: 3
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
Specifies the name of the zone file.
This parameter is only relevant for file-backed DNS.

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

[Restore-DnsServerPrimaryZone](./Restore-DnsServerPrimaryZone.md)

[Set-DnsServerPrimaryZone](./Set-DnsServerPrimaryZone.md)

