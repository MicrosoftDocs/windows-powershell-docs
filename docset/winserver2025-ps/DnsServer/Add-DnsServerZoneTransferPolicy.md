---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_DnsServerZoneTransferPolicy_v1.0.0.cdxml-help.xml
Module Name: DnsServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dnsserver/add-dnsserverzonetransferpolicy?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-DnsServerZoneTransferPolicy
---

# Add-DnsServerZoneTransferPolicy

## SYNOPSIS
Adds a zone transfer policy to a DNS server.

## SYNTAX

### Server (Default)
```
Add-DnsServerZoneTransferPolicy [-ComputerName <String>] [-PassThru] [[-Action] <String>]
 [-ClientSubnet <String>] [[-Condition] <String>] [-InternetProtocol <String>] [-Disable] [-Name] <String>
 [-ProcessingOrder <UInt32>] [-ServerInterfaceIP <String>] [-TimeOfDay <String>] [-TransportProtocol <String>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Zone
```
Add-DnsServerZoneTransferPolicy [-ComputerName <String>] [-PassThru] [-ZoneName] <String> [[-Action] <String>]
 [-ClientSubnet <String>] [[-Condition] <String>] [-InternetProtocol <String>] [-Disable] [-Name] <String>
 [-ProcessingOrder <UInt32>] [-ServerInterfaceIP <String>] [-TimeOfDay <String>] [-TransportProtocol <String>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject
```
Add-DnsServerZoneTransferPolicy [-ComputerName <String>] [-PassThru] [-InputObject] <CimInstance>
 [[-ZoneName] <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Add-DnsServerZoneTransferPolicy** cmdlet adds a zone transfer policy to a Domain Name System (DNS) server.
A policy determines zone transfers based on criteria that you specify in the policy.

A policy consists of criteria and action.

The criteria are a logical combination of client subnet, server interface IP address, fully qualified domain name (FQDN), Internet Protocol (IPv4/IPv6), transport protocol (UDP/TCP), time of day, and query type.

Specify criteria in the following format:

operator, value01, value02, .
. .
, operator, value03, value04, .
. .

The operator is either EQ or NE.
You can specify no more than one of each operator in a criterion.

The policy treats values that follow the EQ operator as multiple assertions which are logically combined (OR'd).
The policy treats values that follow the NE operator as multiple assertions which are logically differenced (AND'd).

This cmdlet combines multiple criteria by using the value of the *Condition* parameter as the logical operator.
This parameter takes one of the following values:

- OR.
The policy evaluates criteria as multiple assertions which are logically combined (OR'd).
- AND.
The policy evaluates criteria as multiple assertions which are logically differenced (AND'd).

If a query meets the criteria of a policy, the action is the response that the policy requires.
You can specify DENY or IGNORE.

You can create policies for zone transfer at either the server level or the zone level.
Server level policies apply on every zone transfer query that occurs on the DNS server.
Zone level policies apply only on the queries on a zone hosted on the DNS server.
The most common use for zone level policies is to implement blocked or safe lists.

Zone level policies apply to the zone in which you create them.
You cannot create a zone level policy without a zone.
If you remove a zone, that removal deletes the associated zone level policies.

## EXAMPLES

### Example 1: Create a server level zone transfer policy
```
PS C:\> Add-DnsServerClientSubnet -Name "AllowedSubnet" -IPv4Subnet 172.21.33.0/24 -PassThru
PS C:\> Add-DnsServerZoneTransferPolicy -Name "NorthAmericaPolicy" -Action IGNORE -ClientSubnet "ne,AllowedSubnet" -PassThru | Format-List *
Name                                             IPV4Subnet                                       IPV6Subnet
----                                             ----------                                       ----------
AllowedSubnet                                    {172.21.33.0/24}



Action                : Ignore
AppliesOn             : ZoneTransfer
Condition             : And
Content               :
Criteria              : {DnsServerPolicyCriteria}
IsEnabled             : True
Level                 : Server
Name                  : NorthAmericaPolicy
ProcessingOrder       : 1
ZoneName              :
PSComputerName        :
CimClass              : root/Microsoft/Windows/DNS:DnsServerPolicy
CimInstanceProperties : {Action, AppliesOn, Condition, Content...}
CimSystemProperties   : Microsoft.Management.Infrastructure.CimSystemProperties
```

The first command creates a client subnet named AllowedSubnet by using the **Add-DnsServerClientSubnet** cmdlet.
That subnet includes the specified IP subnet.

The second command creates a zone transfer policy that disallows all customers that do not belong to the AllowedSubnet subnet.
This policy is a server level policy, and, so, it applies on all the zones on the server.

### Example 2: Disallow zone transfers by server interface
```
PS C:\> Add-DnsServerZoneTransferPolicy -Name "InternalTransfers" -Action IGNORE -ServerInterfaceIP "ne,10.0.0.33" -PassThru
Name                                 ProcessingOrder                      IsEnabled                            Action
----                                 ---------------                      ---------                            ------
internalTransfers1                   3                                    True                                 Ignore
```

This command creates a zone transfer policy that disallows all zone transfer queries that do not arrive  on server interface 10.0.0.33.

### Example 3: Create a zone level zone transfer policy
```
PS C:\> Add-DnsServerZoneTransferPolicy -Name "InternalTransfers" -Action IGNORE -ServerInterfaceIP "ne,10.0.0.33" -PassThru -ZoneName "contoso.com" | Format-List *
Action                : Ignore
AppliesOn             : ZoneTransfer
Condition             : And
Content               :
Criteria              : {DnsServerPolicyCriteria}
IsEnabled             : True
Level                 : Zone
Name                  : InternalTransfers
ProcessingOrder       : 1
ZoneName              : contoso.com
PSComputerName        :
CimClass              : root/Microsoft/Windows/DNS:DnsServerPolicy
CimInstanceProperties : {Action, AppliesOn, Condition, Content...}
CimSystemProperties   : Microsoft.Management.Infrastructure.CimSystemProperties
```

This command creates a zone level zone transfer policy for contoso.com.

## PARAMETERS

### -Action
Specifies the action to take if a zone transfer matches this policy.
The acceptable values for this parameter are:

- DENY.
Respond with SERV_FAIL.
- IGNORE.
Do not respond.

```yaml
Type: String
Parameter Sets: Server, Zone
Aliases:
Accepted values: DENY, IGNORE

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

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
For more information, see **Add-DnsServerClientSubnet**.
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

Example criterion: `"EQ,NorthAmerica,Asia,NE,Europe"`

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
Position: 4
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

### -Disable
Indicates that this cmdlet disables the policy.
If you do not specify this parameter, the cmdlet creates the policy and enables it.

```yaml
Type: SwitchParameter
Parameter Sets: Server, Zone
Aliases:

Required: False
Position: Named
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
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -InternetProtocol
Specifies the Internet Protocol criterion.
Valid values are: IPv4 and IPv6.
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

Example criteria: `"EQ,IPv4"` and `"EQ,IPv6"`

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
Specifies a name for the new policy.

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

Example criteria: `"EQ,10.0.0.1"` and `"NE,192.168.1.1"`

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

Example criterion: `"EQ,10:00-12:00,22:00-23:00"`

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
Valid values are: TCP and UDP.
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

Example criterion: `"EQ,TCP,NE,UDP"`

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
Specifies the name of a DNS zone on which this cmdlet creates a zone level policy.
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

[Get-DnsServerZoneTransferPolicy](./Get-DnsServerZoneTransferPolicy.md)

[Remove-DnsServerZoneTransferPolicy](./Remove-DnsServerZoneTransferPolicy.md)

[Set-DnsServerZoneTransferPolicy](./Set-DnsServerZoneTransferPolicy.md)

[Start-DnsServerZoneTransfer](./Start-DnsServerZoneTransfer.md)

[Add-DnsServerClientSubnet](./Add-DnsServerClientSubnet.md)

[Add-DnsServerQueryResolutionPolicy](./Add-DnsServerQueryResolutionPolicy.md)

