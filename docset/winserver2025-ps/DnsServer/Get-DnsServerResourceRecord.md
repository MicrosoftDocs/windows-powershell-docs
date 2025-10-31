---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_DnsServerResourceRecord_v1.0.0.cdxml-help.xml
Module Name: DnsServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dnsserver/get-dnsserverresourcerecord?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-DnsServerResourceRecord
---

# Get-DnsServerResourceRecord

## SYNOPSIS
Gets resource records from a specified DNS zone.

## SYNTAX

### Unknown
```
Get-DnsServerResourceRecord [[-Name] <String>] [-ComputerName <String>] [-ZoneName] <String> [-Node]
 [-ZoneScope <String>] [-VirtualizationInstance <String>] [-Type] <UInt16> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### Name
```
Get-DnsServerResourceRecord [[-Name] <String>] [-ComputerName <String>] [-ZoneName] <String> [-Node]
 [-ZoneScope <String>] [-VirtualizationInstance <String>] [-RRType <String>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-DnsServerResourceRecord** cmdlet gets the following information for a specified resource record from a Domain Name System (DNS) zone:

- **HostName**
- **RecordType**
- **RecordClass**
- **TimeToLive**
- **Timestamp**
- **RecordData**

## EXAMPLES

### Example 1: Get all resource records in a specified zone
```
PS C:\> Get-DnsServerResourceRecord -ZoneName "contoso.com"
```

This command gets all DNS server resource records in a zone named contoso.com.

### Example 2: Get all resource records in a zone for a specified node
```
PS C:\> Get-DnsServerResourceRecord -ZoneName "contoso.com" -Name "Admin01"
```

This command gets all DNS server resource records in a zone named contoso.com from the node named Admin01.

### Example 3: Get all resource records in a zone by specified host name
```
PS C:\> Get-DnsServerResourceRecord -ZoneName "contoso.com" -Name "Host02"
```

This command gets all DNS server resource records in a zone named contoso.com that have the name Host02.
The command is similar to the one in example 2, but in this case the command uses a host name instead of a node name.

### Example 4: Get all A records in a zone by specified host and specified type
```
PS C:\> Get-DnsServerResourceRecord -ZoneName "contoso.com" -Name "Host03" -RRType "A"
```

This command gets all A records in a zone named contoso.com that have the name Host03.

### Example 5: Get all A records in a specified zone
```
PS C:\> Get-DnsServerResourceRecord -ZoneName "contoso.com" -RRType "A"
```

This command gets all A records in a zone named contoso.com.

### Example 6: Get all NS records at the root of a specified zone
```
PS C:\> Get-DnsServerResourceRecord -ZoneName "contoso.com" -RRType "NS" -Node
```

This command gets all NS records at the root of a zone named contoso.com.

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
Aliases: Cn, ForwardLookupPrimaryServer

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies a node name within the selected zone.
If not specified, it defaults to the root (@) node.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Node
Indicates that the command returns only the resource records at the root of the node specified by the *Name* parameter.
If **Node** is not specified then both the root and any child records in the node are returned.

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

### -RRType
Specifies the type of resource record.

The acceptable values for this parameter are:

- HInfo
- Afsdb
- Atma
- Isdn
- Key
- Mb
- Md
- Mf
- Mg
- MInfo
- Mr
- Mx
- NsNxt
- Rp
- Rt
- Wks
- X25
- A
- AAAA
- CName
- Ptr
- Srv
- Txt
- Wins
- WinsR
- Ns
- Soa
- NasP
- NasPtr
- DName
- Gpos
- Loc
- DhcId
- Naptr
- RRSig
- DnsKey
- DS
- NSec
- NSec3
- NSec3Param

```yaml
Type: String
Parameter Sets: Name
Aliases:
Accepted values: HInfo, Afsdb, Atma, Isdn, Key, Mb, Md, Mf, Mg, MInfo, Mr, Mx, NsNxt, Rp, Rt, Wks, X25, A, AAAA, CName, Ptr, Srv, Txt, Wins, WinsR, Ns, Soa, NasP, NasPtr, DName, Gpos, Loc, DhcId, Naptr, RRSig, DnsKey, DS, NSec, NSec3, NSec3Param, Tlsa

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

### -Type
Specifies a type of record to get.

```yaml
Type: UInt16
Parameter Sets: Unknown
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VirtualizationInstance
Specifies the virtualization instance in which the zone will be added.
A virtualization instance is logical partition in a DNS Server, which is capable of independently hosting zones and zone scopes.
Same name zones and zone scopes can be hosted in different virtualization instances.
This parameter is optional and if not provided it will add the zone into the default virtualization instance which is functionally equivalent to a standard DNS server.

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

### -ZoneName
Specifies the name of a DNS server zone.

```yaml
Type: String
Parameter Sets: (All)
Aliases: ForwardLookupZone

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ZoneScope
Specifies the name of a zone scope.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#DnsServerResourceRecord[]

## NOTES

## RELATED LINKS

[Set-DnsServerResourceRecord](./Set-DnsServerResourceRecord.md)

[Add-DnsServerResourceRecord](./Add-DnsServerResourceRecord.md)

[Remove-DnsServerResourceRecord](./Remove-DnsServerResourceRecord.md)

