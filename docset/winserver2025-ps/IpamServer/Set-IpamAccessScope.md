---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: IpamAccessScope.cdxml-help.xml
Module Name: IpamServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/ipamserver/set-ipamaccessscope?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-IpamAccessScope
---

# Set-IpamAccessScope

## SYNOPSIS
Configures an IPAM access scope.

## SYNTAX

### SetRange
```
Set-IpamAccessScope [-IpamRange] [-AccessScopePath <String>] [-IsInheritedAccessScope]
 -InputObject <CimInstance[]> [-PassThru] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### SetDnsServer
```
Set-IpamAccessScope [-AccessScopePath <String>] [-IsInheritedAccessScope] -InputObject <CimInstance[]>
 [-PassThru] [-IpamDnsServer] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### SetDhcpServer
```
Set-IpamAccessScope [-AccessScopePath <String>] [-IsInheritedAccessScope] -InputObject <CimInstance[]>
 [-PassThru] [-IpamDhcpServer] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### SetDhcpSuperscope
```
Set-IpamAccessScope [-AccessScopePath <String>] [-IsInheritedAccessScope] -InputObject <CimInstance[]>
 [-PassThru] [-IpamDhcpSuperscope] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### SetDhcpScope
```
Set-IpamAccessScope [-AccessScopePath <String>] [-IsInheritedAccessScope] -InputObject <CimInstance[]>
 [-PassThru] [-IpamDhcpScope] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### SetDnsConditionalForwarder
```
Set-IpamAccessScope [-AccessScopePath <String>] [-IsInheritedAccessScope] -InputObject <CimInstance[]>
 [-PassThru] [-IpamDnsConditionalForwarder] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### SetDnsResourceRecord
```
Set-IpamAccessScope [-AccessScopePath <String>] [-IsInheritedAccessScope] -InputObject <CimInstance[]>
 [-PassThru] [-IpamDnsResourceRecord] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### SetDnsZone
```
Set-IpamAccessScope [-AccessScopePath <String>] [-IsInheritedAccessScope] -InputObject <CimInstance[]>
 [-PassThru] [-IpamDnsZone] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### SetAddressSpace
```
Set-IpamAccessScope [-AccessScopePath <String>] [-IsInheritedAccessScope] -InputObject <CimInstance[]>
 [-PassThru] [-IpamAddressSpace] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### SetSubnet
```
Set-IpamAccessScope [-AccessScopePath <String>] [-IsInheritedAccessScope] -InputObject <CimInstance[]>
 [-PassThru] [-IpamSubnet] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### SetBlock
```
Set-IpamAccessScope [-AccessScopePath <String>] [-IsInheritedAccessScope] -InputObject <CimInstance[]>
 [-PassThru] [-IpamBlock] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-IpamAccessScope** configures an IP Address Management (IPAM) server access scope.
Access scopes are used to manage permissions to IPAM objects such as Domain Name System (DNS) servers, Dynamic Host Configuration Protocol (DHCP) scopes, IP address ranges, etc..

When you install IPAM a global scope is automatically created for you.
By default, users with permissions to the global scope have access to all the items in the IPAM infrastructure.
To provide more control over access permissions you can create subscopes such as a geographic location or job role.
You can use the **Set-IpamAccessScope** cmdlet to assign access scopes to specific IPAM objects.

The IPAM objects on which the access scope is to be set is provided in **InputObject** parameter.

## EXAMPLES

### Example 1: Configure an access scope
```
PS C:\> $Zone = Get-IpamDnsZone -ZoneType Forward -ZoneName "dublin.contoso.com"
PS C:\> Set-IpamAccessScope -IpamDnsZone -InputObject $Zone -AccessScopePath "\Global\Europe" -PassThru
```

The first command gets the IPAM DNS zone named dublin.contoso.com and stores it in the variable named $Zone.
The second command adds DHCP scopes and superscopes to the access scope Global\Europe.

The command includes the *PassThru* parameter, so it displays results to the console.Universal Time Coordinate

## PARAMETERS

### -AccessScopePath
Specifies the path to the access scope.
All access scopes must be children of the global scope.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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
The acceptable values for this parameter are:

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
Type: CimInstance[]
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IpamAddressSpace
Indicates that the access scope is assigned to the IPAM address space object.
An address space contains IP blocks, IP subnets, IP ranges, and IP addresses.

```yaml
Type: SwitchParameter
Parameter Sets: SetAddressSpace
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IpamBlock
Indicates that the access scope is assigned to the IP address block object.
An IP address block is the largest unit used for address space management, and is comprised of smaller units called IP address ranges.

```yaml
Type: SwitchParameter
Parameter Sets: SetBlock
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IpamDhcpScope
Indicates that the access scope is assigned to the DHCP scope object.

```yaml
Type: SwitchParameter
Parameter Sets: SetDhcpScope
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IpamDhcpServer
Indicates that the access scope is assigned to DHCP servers.

```yaml
Type: SwitchParameter
Parameter Sets: SetDhcpServer
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IpamDhcpSuperscope
Indicates that the access scope is assigned to DHCP superscopes.

```yaml
Type: SwitchParameter
Parameter Sets: SetDhcpSuperscope
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IpamDnsConditionalForwarder
Indicates that the access scope is assigned to DNS conditional forwarders.

```yaml
Type: SwitchParameter
Parameter Sets: SetDnsConditionalForwarder
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IpamDnsResourceRecord
Indicates that the access scope is assigned to DNS resource records.

```yaml
Type: SwitchParameter
Parameter Sets: SetDnsResourceRecord
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IpamDnsServer
Indicates that the access scope is assigned to DNS servers.

```yaml
Type: SwitchParameter
Parameter Sets: SetDnsServer
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IpamDnsZone
Indicates that the access scope is assigned to DNS zones.

```yaml
Type: SwitchParameter
Parameter Sets: SetDnsZone
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IpamRange
Indicates that the access scope is assigned to IPv4 or IPv6 address ranges.
Address ranges are collections of IP addresses based on characteristics such as address family and starting/ending addresses.

```yaml
Type: SwitchParameter
Parameter Sets: SetRange
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IpamSubnet
Indicates that the access scope is assigned to IP subnets.

```yaml
Type: SwitchParameter
Parameter Sets: SetSubnet
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IsInheritedAccessScope
Indicates that the input object is assigned to the access scope of its parent object.
For example, if the input object is DNS resource record, its access scope will be set to the access scope of the DNS zone the resource record is part of.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[IP Address Management (IPAM) Server Cmdlets in Windows PowerShell](./ipamserver.md)

