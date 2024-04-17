---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: IpamDnsConditionalForwarder.cdxml-help.xml
Module Name: IpamServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/ipamserver/get-ipamdnsconditionalforwarder?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-IpamDnsConditionalForwarder
---

# Get-IpamDnsConditionalForwarder

## SYNOPSIS
Gets information about DNS conditional forwarders from IPAM database.

## SYNTAX

```
Get-IpamDnsConditionalForwarder [[-ConditionalForwarderName] <String[]>] [[-ServerFqdn] <String[]>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-IpamDnsConditionalForwarder** cmdlet gets information about the Domain Name System (DNS) conditional forwarders found in the IP Address Management (IPAM) database.
Conditional forwarders forward queries to a specific DNS server based on the DNS domain names used in those queries.

## EXAMPLES

### Example 1: Get information about all conditional forwarders
```
PS C:\> Get-IpamDnsConditionalForwarder
```

This command gets information about all the conditional forwarders in the IPAM database.

### Example 2: Get information about a specific conditional forwarder
```
PS C:\> Get-IpamDnsConditionalForwarder -ConditionalForwarderName "contoso-internal.com"
```

This command gets information about the conditional forwarder named contoso-internal.com.

### Example 3: Get information about all the conditional forwarders on a server
```
PS C:\> Get-IpamDnsConditionalForwarder -ServerFqdn "dns.contoso.com"
```

This command gets information about all the conditional forwarders found on the server named dns.contoso.com.

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

### -ConditionalForwarderName
Specifies the name, as a string array, of the conditional forwarderthat this cmdlet gets.
For example:

`-ConditionalForwarderName "contoso-test.com"`

``

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ServerFqdn
Specifies the fully qualified domain name (FQDN) of the DNS server hosting the conditional forwarder that this cmdlet gets.
For example:

`-ServerFqdn "dns.contoso.com"`

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### IpamDnsConditionalForwarder

This cmdlet returns an object that represents an instance of the **IpamDnsConditionalForwarder** object.

## NOTES

## RELATED LINKS

[Get-IpamDnsResourceRecord](./Get-IpamDnsResourceRecord.md)

[Get-IpamDnsServer](./Get-IpamDnsServer.md)

[Get-IpamDnsZone](./Get-IpamDnsZone.md)
