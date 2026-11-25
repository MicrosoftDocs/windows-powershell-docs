---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_DnsServerSecondaryZone_v1.0.0.cdxml-help.xml
Module Name: DnsServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dnsserver/add-dnsserversecondaryzone?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-DnsServerSecondaryZone
---

# Add-DnsServerSecondaryZone

## SYNOPSIS
Adds a DNS server secondary zone.

## SYNTAX

### ForwardLookupZone (Default)
```
Add-DnsServerSecondaryZone [-LoadExisting] [-MasterServers] <IPAddress[]> [-ComputerName <String>] [-PassThru]
 [-Name] <String> [-ZoneFile] <String> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### ReverseLookupZone
```
Add-DnsServerSecondaryZone [-LoadExisting] [-MasterServers] <IPAddress[]> [-ComputerName <String>] [-PassThru]
 [-ZoneFile] <String> -NetworkId <String> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Add-DnsServerSecondaryZone** cmdlet adds a specified secondary zone on a Domain Name System (DNS) server.
You can create either a forward lookup zone or a reverse lookup zone.
To create a reverse lookup zone, specify a network ID by using the *NetworkID* parameter, or specify a full reverse lookup zone name by using the *Name* parameter.

## EXAMPLES

### Example 1: Add a secondary DNS server zone
```
PS C:\> Add-DnsServerSecondaryZone -Name "western.contoso.com" -ZoneFile "western.contoso.com.dns" -MasterServers 172.23.90.124
```

This command creates a secondary DNS zone named western.contoso.com with the specified master server.
This zone is file-backed.

### Example 2: Create secondary zones
```
PS C:\> Get-DnsServerZone -ComputerName win-olpn33s5q3m.mytest.contoso.com | where {("Primary" -eq $_.ZoneType) -and ($False -eq $_.IsAutoCreated) -and ("TrustAnchors" -ne $_.ZoneName)} | %{ $_ | Add-DnsServerSecondaryZone -MasterServers 172.23.90.136 -ZoneFile "$($_.ZoneName).dns"}
```

This example gets primary zones from the server win-olpn33s5q3m.mytest.contoso.com and creates secondary zones, except TrustAnchors and AutoCreated zones, on the local system.

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

### -LoadExisting
Indicates that the server loads an existing file for the zone.
If you do not specify this parameter, this cmdlet creates default zone records automatically.
This parameter is relevant only for file-backed zones.

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
Parameter Sets: ForwardLookupZone
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
Parameter Sets: ReverseLookupZone
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
This parameter is only relevant for file-backed DNS.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#DnsServerSecondaryZone

## NOTES

## RELATED LINKS

[ConvertTo-DnsServerSecondaryZone](./ConvertTo-DnsServerSecondaryZone.md)

[Restore-DnsServerSecondaryZone](./Restore-DnsServerSecondaryZone.md)

[Set-DnsServerSecondaryZone](./Set-DnsServerSecondaryZone.md)

