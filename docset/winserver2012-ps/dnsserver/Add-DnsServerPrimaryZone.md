---
external help file: DnsServer_Cmdlets.xml
Module Name: DnsServer
online version: https://learn.microsoft.com/powershell/module/dnsserver/add-dnsserverprimaryzone?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Add-DnsServerPrimaryZone

## SYNOPSIS
Adds a primary zone to a DNS server.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Add-DnsServerPrimaryZone [-Name] <String> [-ReplicationScope] <String> [[-DirectoryPartitionName] <String>]
 [-AsJob] [-CimSession <CimSession[]>] [-ComputerName <String>] [-DynamicUpdate <String>] [-LoadExisting]
 [-PassThru] [-ResponsiblePerson <String>] [-ThrottleLimit <Int32>] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Add-DnsServerPrimaryZone [-Name] <String> [-AsJob] [-CimSession <CimSession[]>] [-ComputerName <String>]
 [-DynamicUpdate <String>] [-LoadExisting] [-PassThru] [-ResponsiblePerson <String>] [-ThrottleLimit <Int32>]
 -ZoneFile <String> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_3
```
Add-DnsServerPrimaryZone [-ReplicationScope] <String> [[-DirectoryPartitionName] <String>] [-AsJob]
 [-CimSession <CimSession[]>] [-ComputerName <String>] [-DynamicUpdate <String>] [-LoadExisting] [-PassThru]
 [-ResponsiblePerson <String>] [-ThrottleLimit <Int32>] -NetworkId <String> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_4
```
Add-DnsServerPrimaryZone [-AsJob] [-CimSession <CimSession[]>] [-ComputerName <String>]
 [-DynamicUpdate <String>] [-LoadExisting] [-PassThru] [-ResponsiblePerson <String>] [-ThrottleLimit <Int32>]
 -NetworkId <String> -ZoneFile <String> [-Confirm] [-WhatIf]
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
PS C:\>Add-DnsServerPrimaryZone -Name "west02.contoso.com" -ZoneFile "west02.contoso.com.dns"
```

This command creates a file-backed primary forward lookup zone called west02.contoso.com with the specified DNS file.

### Example 3: Create a reverse lookup zone
```
PS C:\>Add-DnsServerPrimaryZone -NetworkID "10.1.0.0/24" -ReplicationScope "Forest" 
ZoneName                            ZoneType        IsAutoCreated   IsDsIntegrated  IsReverseLookupZone  IsSigned

--------                            --------        -------------   --------------  -------------------  --------

1.10.in-addr.arpa                   Primary         False           True            True                 False
```

This command creates the Active Directory-integrated class C reverse lookup zone 0.1.10.in-addr.arpa with Forest-wide replication scope.

### Example 4: Create a file-backed reverse lookup zone
```
PS C:\>Add-DnsServerPrimaryZone -NetworkID 10.3.0.0/24 -ZoneFile "0.3.10.in-addr.arpa.dns"
```

This command creates the file-backed reverse lookup zone 0.3.10.in-addr.arpa.

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

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: 

Required: False
Position: 4
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

Required: False
Position: Named
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

### -Name
Specifies a name for the zone the cmdlet creates.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2
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
Parameter Sets: UNNAMED_PARAMETER_SET_3, UNNAMED_PARAMETER_SET_4
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
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_3
Aliases: 

Required: True
Position: 3
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

### -ZoneFile
Specifies a name of the zone file.
This parameter is only relevant for file-backed zones.

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

[ConvertTo-DnsServerPrimaryZone](./ConvertTo-DnsServerPrimaryZone.md)

[Restore-DnsServerPrimaryZone](./Restore-DnsServerPrimaryZone.md)

[Set-DnsServerPrimaryZone](./Set-DnsServerPrimaryZone.md)

