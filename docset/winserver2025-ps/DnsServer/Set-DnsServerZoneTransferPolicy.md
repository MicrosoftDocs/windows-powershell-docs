---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_DnsServerZoneTransferPolicy_v1.0.0.cdxml-help.xml
Module Name: DnsServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dnsserver/set-dnsserverzonetransferpolicy?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-DnsServerZoneTransferPolicy
---

# Set-DnsServerZoneTransferPolicy

## SYNOPSIS
Updates a zone transfer policy on a DNS server.

## SYNTAX

### Server (Default)
```
Set-DnsServerZoneTransferPolicy [-PassThru] [-ComputerName <String>] [-ClientSubnet <String>]
 [-Condition <String>] [-InternetProtocol <String>] [-Name] <String> [-ProcessingOrder <UInt32>]
 [-ServerInterfaceIP <String>] [-TimeOfDay <String>] [-TransportProtocol <String>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Zone
```
Set-DnsServerZoneTransferPolicy [-PassThru] [-ComputerName <String>] [-ZoneName] <String>
 [-ClientSubnet <String>] [-Condition <String>] [-InternetProtocol <String>] [-Name] <String>
 [-ProcessingOrder <UInt32>] [-ServerInterfaceIP <String>] [-TimeOfDay <String>] [-TransportProtocol <String>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject
```
Set-DnsServerZoneTransferPolicy [-PassThru] [-ComputerName <String>] [-InputObject] <CimInstance>
 [[-ZoneName] <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-DnsServerZoneTransferPolicy** cmdlet updates a zone transfer policy on a Domain Name System (DNS) server.

## EXAMPLES

### Example 1: Update a zone transfer policy
```
PS C:\> Set-DnsServerZoneTransferPolicy -Name "InternalTransfers" -TransportProtocol "NE,TCP" -ServerInterfaceIP $Null
```

This command updates the zone transfer policy named InternalTransfers.
The command modifies the transport protocol and the server interface IP address criteria.
For the server interface IP address, the command specifies $Null, which removes the previously set criterion.

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

### -ClientSubnet
Specifies the client subnet criterion.
Specify a criterion in the following format:

operator, value01, value02, .
. .
, operator, value03, value04, .
. .

The operator is either EQ or NE.
You can specify no more than one of each operator in a criterion.

The policy treats values that follow the EQ operator as multiple assertions which are logically combined (OR'd).
The policy treats values that follow the NE operator as multiple assertions which are logically differenced (AND'd).
The criterion is satisfied if the subnet of the zone transfer matches one of the EQ values and does not match any of the NE values.

```yaml
Type: String
Parameter Sets: Server, Zone
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### -Condition
Specifies how the policy treats multiple criteria.
The acceptable values for this parameter are:

- OR.
The policy evaluates criteria as multiple assertions which are logically combined (OR'd).
- AND.
The policy evaluates criteria as multiple assertions which are logically differenced (AND'd).

The default value is AND.

```yaml
Type: String
Parameter Sets: Server, Zone
Aliases:
Accepted values: AND, OR

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### -InputObject
Specifies the input to this cmdlet.
You can use this parameter, or you can pipe the input to this cmdlet.

```yaml
Type: CimInstance
Parameter Sets: InputObject
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -InternetProtocol
Specifies the Internet Protocol criterion.
Specify a criterion in the following format:

operator, value01, value02, .
. .
, operator, value03, value04, .
. .

The operator is either EQ or NE.
You can specify no more than one of each operator in a criterion.

The policy treats values that follow the EQ operator as multiple assertions which are logically combined (OR'd).
The policy treats values that follow the NE operator as multiple assertions which are logically differenced (AND'd).
The criterion is satisfied if the IP address of the zone transfer matches one of the EQ values and does not match any of the NE values.

```yaml
Type: String
Parameter Sets: Server, Zone
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the name of the policy to update.

```yaml
Type: String
Parameter Sets: Server, Zone
Aliases:

Required: True
Position: 1
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

### -ProcessingOrder
Specifies the precedence of the policy.
Higher integer values have lower precedence.
By default, this cmdlet adds a new policy as the lowest precedence.

```yaml
Type: UInt32
Parameter Sets: Server, Zone
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ServerInterfaceIP
Specifies the IP address of the server interface on which the DNS server listens.
Specify a criterion in the following format:

operator, value01, value02, .
. .
, operator, value03, value04, .
. .

The operator is either EQ or NE.
You can specify no more than one of each operator in the criterion.

The policy treats values the follow the EQ operator as multiple assertions which are logically combined (OR'd).
The policy treats values that follow the NE operator as multiple assertions which are logically differenced (AND'd).
The criterion is satisfied if the IP address of the interface matches one of the EQ values and does not match any of the NE values.

```yaml
Type: String
Parameter Sets: Server, Zone
Aliases:

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

### -TimeOfDay
Specifies the time of day criterion.
Specify a criterion in the following format:

operator, value01, value02, .
. .
, operator, value03, value04, .
. .

The operator is either EQ or NE.
You can specify no more than one of each operator in the criterion.

The policy treats values the follow the EQ operator as multiple assertions which are logically combined (OR'd).
The policy treats values that follow the NE operator as multiple assertions which are logically differenced (AND'd).
The criterion is satisfied if the time of day of the zone transfer matches one of the EQ values and does not match any of the NE values.

```yaml
Type: String
Parameter Sets: Server, Zone
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TransportProtocol
Specifies the transport protocol criterion.
Specify a criterion in the following format:

operator, value01, value02, .
. .
, operator, value03, value04, .
. .

The operator is either EQ or NE.
You can specify no more than one of each operator in the string.

The policy treats values the follow the EQ operator as multiple assertions which are logically combined (OR'd).
The policy treats values that follow the NE operator as multiple assertions which are logically differenced (AND'd).
The criterion is satisfied if the transport protocol of the zone transfer matches one of the EQ values and does not match any of the NE values.

```yaml
Type: String
Parameter Sets: Server, Zone
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
Specifies the name of a DNS zone on which the zone level policy exists.
The zone must exist on the DNS server.

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

```yaml
Type: String
Parameter Sets: InputObject
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#DnsServerPolicy

## NOTES

## RELATED LINKS

[Add-DnsServerZoneTransferPolicy](./Add-DnsServerZoneTransferPolicy.md)

[Get-DnsServerZoneTransferPolicy](./Get-DnsServerZoneTransferPolicy.md)

[Remove-DnsServerZoneTransferPolicy](./Remove-DnsServerZoneTransferPolicy.md)

[Start-DnsServerZoneTransfer](./Start-DnsServerZoneTransfer.md)

[Add-DnsServerQueryResolutionPolicy](./Add-DnsServerQueryResolutionPolicy.md)

