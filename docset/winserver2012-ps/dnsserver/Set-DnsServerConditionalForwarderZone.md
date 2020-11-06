---
external help file: DnsServer_Cmdlets.xml
online version: 
schema: 2.0.0
ms.assetid: 8925DBAA-CDEE-428B-9FA6-3CF7725C13EE
manager: dansimp
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Set-DnsServerConditionalForwarderZone

## SYNOPSIS
Changes settings for a DNS conditional forwarder.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Set-DnsServerConditionalForwarderZone [-Name] <String> [[-MasterServers] <IPAddress[]>]
 [[-ForwarderTimeout] <UInt32>] [[-UseRecursion] <Boolean>] [-AsJob] [-CimSession <CimSession[]>]
 [-ComputerName <String>] [-PassThru] [-ThrottleLimit <Int32>] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Set-DnsServerConditionalForwarderZone [-Name] <String> [-AsJob] [-CimSession <CimSession[]>]
 [-ComputerName <String>] [-DirectoryPartitionName <String>] [-PassThru] [-ThrottleLimit <Int32>]
 -ReplicationScope <String> [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Set-DnsServerConditionalForwarderZone** cmdlet changes settings of an existing conditional forwarder on a Domain Name System (DNS) server.
You can change the master servers, forwarder time-out, recursion, recursion scope, and directory partition name for a conditional forwarder zone.

## EXAMPLES

### Example 1: Change forwarder time-out for a zone
```
PS C:\> Set-DnsServerConditionalForwarderZone -Name "contoso.com" -ForwarderTimeout 15
```

This command changes the forwarder time-out for a forwarder zone named contoso.com.

### Example 2: Change replication scope for a zone
```
PS C:\>Set-DnsServerConditionalForwarderZone -Name "contoso.com" -ReplicationScope "Domain" -PassThru
```

This command changes the replication scope of contoso.com to a value of Domain, which means all DNS servers in the domain.
This example uses the **PassThru** parameter to create output.

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
Specifies a DNS server to host the forwarder.
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
Specifies a directory partition on which to store the forwarder.
Conditional forwarders are internally stored as zones.
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

### -ForwarderTimeout
Specifies a length of time, in seconds, that a DNS server waits for the forwarder to resolve a query.
After the DNS server tries all forwarders, it can attempt to resolve the query itself.
The minimum value is 0.
The maximum value is 15.

```yaml
Type: UInt32
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MasterServers
Specifies an array of IP addresses of the master servers of the zone.
Conditional forwarders are stored as zones.
You can use both IPv4 and IPv6 addresses.
Specify at least one master server.

```yaml
Type: IPAddress[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the name of a zone that has conditional forwarding configured.

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

### -UseRecursion
Specifies whether a DNS server attempts to resolve a query after the forwarder fails to resolve it.
A value of $False prevents a DNS server from attempting resolution using other DNS servers.
This parameter overrides the Use Recursion setting for a DNS server.

```yaml
Type: Boolean
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: 5
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

### Microsoft.Management.Infrastructure.CimInstance#DnsServerConditionalForwarderZone

## NOTES

## RELATED LINKS

[Add-DnsServerConditionalForwarderZone](./Add-DnsServerConditionalForwarderZone.md)

