---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: IpamDnsZone.cdxml-help.xml
Module Name: IpamServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/ipamserver/get-ipamdnszone?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-IpamDnsZone
---

# Get-IpamDnsZone

## SYNOPSIS
Gets information about DNS zones from IPAM database.

## SYNTAX

```
Get-IpamDnsZone [-ZoneType] <ZoneType[]> [[-ZoneName] <String[]>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-IpamDnsZone** cmdlet gets information about all the Domain Name System (DNS) zones in the IPAM (IP Address Management) server database.
A DNS zone is a distinct section of the domain name system for an organization.
For instance, the DNS zone northamerica.contoso.com would maintain DNS records for contoso.com's northamerica subdomain.
Likewise, the DNS zone southamerica.contoso.com would maintain DNS records for contoso.com's southamerica subdomain.

## EXAMPLES

### Example 1: Get information about all forward zones
```
PS C:\> Get-IpamDnsZone -ZoneType "Forward"
```

This command returns information about all the forward zones in the IPAM database.

### Example 2: Get information about the forward zones in a specific DNS zone
```
PS C:\> Get-IpamDnsZone -ZoneType "Forward" -ZoneName "northamerica.contoso.com"
```

This command returns information for the DNS zone named northamerica.contoso.com.

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
Specifies the name of the DNS zone to be returned.
For example:

`-ZoneName "northamerica.contoso.com"`

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

### -ZoneType
Specifies the type of DNS zone to be returned.

The acceptable values for this parameter are:

- Forward.
Resolves host names to IP addresses.
- IPv4Reverse.
Resolves IPv4 addresses to host names.
- IPv6Reverse.
Resolves IPv6 addresses to host names.

For example:

`-ZoneType "IPv4Reverse"`

```yaml
Type: ZoneType[]
Parameter Sets: (All)
Aliases:
Accepted values: Forward, IPv4Reverse, IPv6Reverse

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

### IpamDnsZone

This cmdlet returns an instance of the **IpamDnsZone** object.

## NOTES

## RELATED LINKS

[Get-IpamDnsConditionalForwarder](./Get-IpamDnsConditionalForwarder.md)

[Get-IpamDnsResourceRecord](./Get-IpamDnsResourceRecord.md)

[Get-IpamDnsServer](./Get-IpamDnsServer.md)
