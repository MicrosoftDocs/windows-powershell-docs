---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_DnsServerZoneTransferPolicy_v1.0.0.cdxml-help.xml
Module Name: DnsServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dnsserver/get-dnsserverzonetransferpolicy?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-DnsServerZoneTransferPolicy
---

# Get-DnsServerZoneTransferPolicy

## SYNOPSIS
Gets the zone transfer policies on a DNS server.

## SYNTAX

### Server (Default)
```
Get-DnsServerZoneTransferPolicy [[-Name] <String>] [-ComputerName <String>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### Zone
```
Get-DnsServerZoneTransferPolicy [[-Name] <String>] [-ComputerName <String>] [-ZoneName] <String>
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-DnsServerZoneTransferPolicy** cmdlet gets zone transfer policies on a Domain Name System (DNS) server.
Specify a zone by name to get zone level policies.
If you do not specify a zone, this cmdlet gets server level policies.

## EXAMPLES

### Example 1: Get all server level zone transfer policies
```
PS C:\> Get-DnsServerZoneTransferPolicy
Name                                 ProcessingOrder                      IsEnabled                            Action
----                                 ---------------                      ---------                            ------
NorthAmericaPolicy                   1                                    True                                 Ignore
InternalTransfers                    2                                    True                                 Ignore
```

This cmdlet gets all the server level zone transfer policies.

### Example 2: Get all zone transfer policies for a zone
```
PS C:\> Get-DnsServerZoneTransferPolicy -ZoneName "contoso.com"
Name                                 ProcessingOrder                      IsEnabled                            Action
----                                 ---------------                      ---------                            ------
InternalTransfers                    1                                    True                                 Ignore
```

This command gets all the zone transfer policies for the zone named contoso.com.

### Example 3: Get a particular zone level policy
```
PS C:\> Get-DnsServerZoneTransferPolicy -ZoneName "contoso.com" -Name "InternalTransfers"
Name                                 ProcessingOrder                      IsEnabled                            Action
----                                 ---------------                      ---------                            ------
InternalTransfers                    1                                    True                                 Ignore
```

This command gets the zone transfer policy named InternalTransfers on the zone named contoso.com.

### Example 4: Get a server level zone transfer policy
```
PS C:\> Get-DnsServerZoneTransferPolicy -Name "InternalTransfers"
Name                                 ProcessingOrder                      IsEnabled                            Action
----                                 ---------------                      ---------                            ------
InternalTransfers                    2                                    True                                 Ignore
```

This command gets the server level zone transfer policy named InternalTransfers.

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
Specifies a remote DNS server.
You can specify an IP address or any value that resolves to an IP address, such as an FQDN, host name, or NETBIOS name.

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

### -Name
Specifies the name of the policy to get.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
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
Specifies the name of a DNS zone.
This cmdlet gets policies from the zone that this parameter specifies.

```yaml
Type: String
Parameter Sets: Zone
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

### Microsoft.Management.Infrastructure.CimInstance#DnsServerPolicy[]

## NOTES

## RELATED LINKS

[Add-DnsServerZoneTransferPolicy](./Add-DnsServerZoneTransferPolicy.md)

[Remove-DnsServerZoneTransferPolicy](./Remove-DnsServerZoneTransferPolicy.md)

[Set-DnsServerZoneTransferPolicy](./Set-DnsServerZoneTransferPolicy.md)

[Start-DnsServerZoneTransfer](./Start-DnsServerZoneTransfer.md)

[Add-DnsServerQueryResolutionPolicy](./Add-DnsServerQueryResolutionPolicy.md)

