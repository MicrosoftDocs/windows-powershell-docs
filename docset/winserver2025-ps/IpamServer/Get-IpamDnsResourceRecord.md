---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: IpamDnsResourceRecord.cdxml-help.xml
Module Name: IpamServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/ipamserver/get-ipamdnsresourcerecord?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-IpamDnsResourceRecord
---

# Get-IpamDnsResourceRecord

## SYNOPSIS
Gets DNS resource records from IPAM database.

## SYNTAX

```
Get-IpamDnsResourceRecord [-ZoneName] <String[]> [[-RecordName] <String[]>]
 [[-RecordType] <DnsResourceRecordType[]>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-IpamDnsResourceRecord** cmdlet gets Domain Name System (DNS) resource records from IP Address Management (IPAM) server database.
Resource records are used to define both the structure and the content of a DNS namespace.
Different DNS elements, such as, a host, a mail exchanger, and a Dynamic Host Configuration Protocol (DHCP) server, will have different types of resource records.

## EXAMPLES

### Example 1: Get information about all the resource records for a zone
```
PS C:\> Get-IpamDnsResourceRecord -ZoneName "northamerica.contoso.com"
```

This command gets all the DNS resource records for the zone named northamerica.contoso.com.

### Example 2: Get information about one type of resource record
```
PS C:\> Get-IpamDnsResourceRecord -ZoneName "northamerica.contoso.com" -RecordType "AAAA"
```

This command gets only the IPv6 DNS resource records of record type AAAA for the zone named northamerica.contoso.com.

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

### -RecordName
Specifies the name of the resource record that this cmdlet gets.
For example:this command returns the resource record with the name host1:

`-RecordName "host1"`

``

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RecordType
Specifies the type of DNS resource records that this cmdlet gets.

The acceptable values for this parameter are:

- A. Address record. Specifies an IPv4 address that is typically used for a host computer.
- AAAA. IPv6 address record. Specifies an IPv6 address that is typically used for a host computer.
- PTR. Pointer record. Specifies a canonical name that is typically used for reverse DNS lookups.
- SOA. Start of authority record. Specifies authoritative information about a DNS zone.
- NS. Name server record. Specifies an authoritative name server for a DNS zone.
- CNAME. Canonical name record that points to a DNS alias.
- DNAME. Delegation name record. Points to a DNS alias and its subnames. This differs from a CNAME record, which points only to an exact name.
- MX. Mail exchange record. Maps a domain name to the mail transfer agents for that domain.
- SRV. Service location record. Specifies the location of services within the domain.
- TXT. Text record. Maintains descriptive text.
- AFSDB. AFS database record. Specifies the location of a database in an Andrew File System cell.
- ATMA. Asynchronous Transfer Mode Address (ATMA) resource record. Maps a DNS domain name in the owner field to an Asynchronous Transfer Mode (ATM) address referenced in the **atm_address** field.
- DHCID. DHCP identifier record. Points to a DHCP server.
- HINFO. System information record. Specifies the host or server's operating system and CPU type.
- ISDN. Integrated Services Digital Network (ISDN) resource record. Maps a domain name to an ISDN telephone number.
- RP. Responsible person record. Maintains information about the person responsible for a domain.
- RT. Route through (RT) resource record. Provides an intermediate host binding for internal hosts that do not have a direct wide area network (WAN) or external network connection.
- WINS. Windows Internet Name Service record.
- WINSR. Windows Internet Name Service reverse-lookup record.
- WKS. Well-known service (WKS) resource record. Describes the well-known TCP/IP services supported by a particular protocol on a specific IP address.
- X25. X-25 resource record. Maps a domain name to a Public Switched Data Network (PSDN) address number.

For example:

`-RecordType "CNAME"`

```yaml
Type: DnsResourceRecordType[]
Parameter Sets: (All)
Aliases:
Accepted values: A, AAAA, PTR, SOA, NS, CNAME, DNAME, MX, SRV, TXT, AFSDB, ATMA, DHCID, HINFO, ISDN, RP, RT, WINS, WINSR, WKS, X25

Required: False
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

### -ZoneName
Specifies the name of the DNS zone that this cmdlet gets resource records from.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### IpamDnsResourceRecord

This cmdlet returns an instance of the **IpamDnsResourceRecord** object.

## NOTES

## RELATED LINKS

[Get-IpamDnsConditionalForwarder](./Get-IpamDnsConditionalForwarder.md)

[Get-IpamDnsServer](./Get-IpamDnsServer.md)

[Get-IpamDnsZone](./Get-IpamDnsZone.md)
