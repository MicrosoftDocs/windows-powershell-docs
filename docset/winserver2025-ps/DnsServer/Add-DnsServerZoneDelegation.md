---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_DnsServerZoneDelegation_v1.0.0.cdxml-help.xml
Module Name: DnsServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dnsserver/add-dnsserverzonedelegation?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-DnsServerZoneDelegation
---

# Add-DnsServerZoneDelegation

## SYNOPSIS
Adds a new delegated DNS zone to an existing zone.

## SYNTAX

### InputObject (Default)
```
Add-DnsServerZoneDelegation [-ComputerName <String>] [-PassThru] [[-ZoneScope] <String>]
 [-InputObject] <CimInstance> [-VirtualizationInstance <String>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Parameters
```
Add-DnsServerZoneDelegation [-ComputerName <String>] [-PassThru] [[-ZoneScope] <String>]
 [-VirtualizationInstance <String>] [-ChildZoneName] <String> [-IPAddress] <IPAddress[]> [-NameServer] <String>
 [-Name] <String> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Add-DnsServerZoneDelegation** cmdlet adds a zone delegation to a Domain Name System (DNS) zone.
For instance, you can add a child domain called west01 to your top level domain, contoso.com, and specify a DNS server for that delegated domain.

## EXAMPLES

### Example 1: Add a zone delegation
```
PS C:\> Add-DnsServerZoneDelegation -Name "contoso.com" -ChildZoneName "west01" -NameServer "wserver.west01.contoso.com" -IPAddress 172.23.90.136 -PassThru -Verbose
```

This command creates a delegation for west01 in the zone contoso.com with the specified name server and IP address.

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

### -ChildZoneName
Specifies a name of the child zone.

```yaml
Type: String
Parameter Sets: Parameters
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### -IPAddress
Specifies an array of IP addresses for DNS servers for the child zone.

```yaml
Type: IPAddress[]
Parameter Sets: Parameters
Aliases:

Required: True
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Position: 2
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Specifies the name of the parent zone.
The child zone is part of this zone.

```yaml
Type: String
Parameter Sets: Parameters
Aliases: ZoneName

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NameServer
Specifies the name of the DNS server that hosts the child zone.

```yaml
Type: String
Parameter Sets: Parameters
Aliases:

Required: True
Position: 3
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

### -ZoneScope
Specifies the name of a zone scope.

If you do not specify this parameter, the cmdlet adds the delegation into the default scope of the zone.
We recommend that you add the delegations in all available scopes.
Not adding delegations in all scopes causes loss in visibility to the child domains by means of certain scopes of parent zone where you do not add delegation.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 5
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#DnsServerZoneDelegation

## NOTES

## RELATED LINKS

[Get-DnsServerZoneDelegation](./Get-DnsServerZoneDelegation.md)

[Remove-DnsServerZoneDelegation](./Remove-DnsServerZoneDelegation.md)

[Set-DnsServerZoneDelegation](./Set-DnsServerZoneDelegation.md)

