---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_DnsServerResourceRecord_v1.0.0.cdxml-help.xml
Module Name: DnsServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dnsserver/remove-dnsserverresourcerecord?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-DnsServerResourceRecord
---

# Remove-DnsServerResourceRecord

## SYNOPSIS
Removes specified DNS server resource records from a zone.

## SYNTAX

### InputObject (Default)
```
Remove-DnsServerResourceRecord [-ZoneName] <String> [-PassThru] [-ComputerName <String>] [-Force]
 [-ZoneScope <String>] [-VirtualizationInstance <String>] -InputObject <CimInstance>
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Unknown
```
Remove-DnsServerResourceRecord [-ZoneName] <String> [-PassThru] [-ComputerName <String>] [-Force]
 [-ZoneScope <String>] [-VirtualizationInstance <String>] [-RecordData <String[]>] [-Name] <String>
 [-Type] <UInt16> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### Name
```
Remove-DnsServerResourceRecord [-ZoneName] <String> [-PassThru] [-ComputerName <String>] [-Force]
 [-ZoneScope <String>] [-VirtualizationInstance <String>] [-RRType] <String> [-RecordData <String[]>]
 [-Name] <String> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Remove-DnsServerResourceRecord** cmdlet removes resource record objects from a Domain Name System (DNS) zone.

You can either use the **Get-DnsServerResourceRecord** cmdlet to specify an object, or you can specify the **RRtype**, **Name** and **RecordData** of the resource record you want to remove.
If you specify an **RRtype** or name and there are multiple resource records, you can specify the **RecordData** to delete a specific record.
If you do not specify **RecordData**, the cmdlet deletes all records that match **RRtype** and **Name** for the specified zone.

## EXAMPLES

### Example 1: Remove all root hints
```
PS C:\> Get-DnsServerResourceRecord -ZoneName "..roothints" | Remove-DnsServerResourceRecord -Force -ZoneName "..roothints"
```

This command removes all root hints for a DNS server.

### Example 2: Remove multiple A records
```
PS C:\> Remove-DnsServerResourceRecord -ZoneName "contoso.com" -RRType "A" -Name "Host01"

Confirm
Removing DNS resource record Host01 of type A from zone contoso.com on ROOT server. Do you want to continue?
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"): n
```

This command removes all A resource records in the contoso.com zone that have the name Host01.

### Example 3: Remove an A record
```
PS C:\> Remove-DnsServerResourceRecord -ZoneName "contoso.com" -RRType "A" -Name "Host01" -RecordData "10.17.1.41"
```

This command removes the A resource record from a zone named contoso.com that has the name Host01 and the IP address 10.17.1.41.

### Example 4: Remove multiple SRV records
```
PS C:\> Remove-DnsServerResourceRecord -RRType SRV -Name "_misc._tcp" -ZoneName "_msdcs.contoso.com" -RecordData "0","10","1234","1.1.1.1."
```

This command removes all SRV records in the _msdcs.contoso.com zone that have the name _misc._tcp.

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

### -Force
Removes a record or records without prompting you for confirmation.
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

### -InputObject
Specifies the input to this cmdlet.
You can use this parameter, or you can pipe the input to this cmdlet.

```yaml
Type: CimInstance
Parameter Sets: InputObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Specifies the name of a DNS server resource record object.

```yaml
Type: String
Parameter Sets: Unknown, Name
Aliases: RecordName

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

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RecordData
Specifies the data contained in the resource record you want to delete.

```yaml
Type: String[]
Parameter Sets: Unknown, Name
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

### -Type
Specifies the type of record to remove.

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

### -ZoneName
Specifies the name of a DNS zone.

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

### Microsoft.Management.Infrastructure.CimInstance#DnsServerResourceRecord[]

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#DnsServerResourceRecord[]

## NOTES

## RELATED LINKS

[Get-DnsServerResourceRecord](./Get-DnsServerResourceRecord.md)

[Set-DnsServerResourceRecord](./Set-DnsServerResourceRecord.md)

[Add-DnsServerResourceRecord](./Add-DnsServerResourceRecord.md)
