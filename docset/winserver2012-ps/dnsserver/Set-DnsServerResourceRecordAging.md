---
external help file: DnsServer_Cmdlets.xml
online version: 
schema: 2.0.0
ms.assetid: F5AD1594-6D98-42E2-8C37-3860912ED276
manager: dansimp
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Set-DnsServerResourceRecordAging

## SYNOPSIS
Begins aging of resource records in a specified DNS zone.

## SYNTAX

```
Set-DnsServerResourceRecordAging [-ZoneName] <String> [[-NodeName] <String>] [-AsJob]
 [-CimSession <CimSession[]>] [-ComputerName <String>] [-Force] [-Recurse] [-ThrottleLimit <Int32>] [-Confirm]
 [-WhatIf]
```

## DESCRIPTION
The **Set-DnsServerResourceRecordAging** cmdlet ages Domain Name System (DNS) resource records in a DNS zone.
You must enable aging at the zone level by using the Set-DnsServerZoneAging cmdlet.

A resource record can remain after the resource is no longer part of the network.
Aging settings determine when a record can be removed as stale.
After that time, designated DNS servers can remove, or scavenge, a stale record.

This cmdlet sets a time stamp to the current time for records in a specified zone on the specified DNS server, if you have enabled aging for the zone.

## EXAMPLES

### Example 1: Age records in a zone
```
PS C:\> Set-DnsServerResourceRecordAging -ZoneName "contoso.com" -Force -Recurse
```

This command ages all the records under contoso.com, recursively.
The **Force** parameter overrides the default confirmation message.

### Example 2: Age records under a node
```
PS C:\>Set-DnsServerResourceRecordAging -NodeName "three.two" -ZoneName "contoso.com"
```

This command ages all the records under the three.two node in the zone contoso.com.

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

### -Force
Performs the action without a confirmation message.

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

### -NodeName
Specifies a node or subtree in DNS zone.
The acceptable values for this parameter are:

- @ for root node.
- The FQDN of a node (the name with a period (.) at the end). 
- A single label for the name relative to the zone root.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Recurse
Indicates that the DNS server ages all the nodes under the specified node.
Use this parameter to age all records in a zone.

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

### -ZoneName
Specifies the name of a DNS zone.

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

## NOTES

## RELATED LINKS

[Get-DnsServerZoneAging](./Get-DnsServerZoneAging.md)

[Set-DnsServerZoneAging](./Set-DnsServerZoneAging.md)

