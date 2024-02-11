---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_DhcpServerV4Scope_v1.0.0.cdxml-help.xml
Module Name: DhcpServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dhcpserver/add-dhcpserverv4scope?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-DhcpServerv4Scope
---

# Add-DhcpServerv4Scope

## SYNOPSIS
Adds an IPv4 scope on the DHCP server service.

## SYNTAX

```
Add-DhcpServerv4Scope [-ComputerName <String>] [-StartRange] <IPAddress> [-EndRange] <IPAddress>
 [-Name] <String> [-Description <String>] [-State <String>] [-SuperscopeName <String>]
 [-MaxBootpClients <UInt32>] [-ActivatePolicies <Boolean>] [-PassThru] [-NapEnable] [-NapProfile <String>]
 [-Delay <UInt16>] [-LeaseDuration <TimeSpan>] [-SubnetMask] <IPAddress> [-Type <String>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Add-DhcpServerv4Scope** cmdlet adds an IPv4 scope on the Dynamic Host Configuration Protocol (DHCP) server service that has the specified parameters.

## EXAMPLES

### Example 1: Add a new scope for a subnet
```
PS C:\> Add-DhcpServerv4Scope -Name "Lab-4 Network" -StartRange 10.10.10.1 -EndRange 10.10.10.254 -SubnetMask 255.255.255.0
```

This example adds a new scope for 10.10.10.0/24 subnet on the DHCP server service that runs on the local computer.

### Example 2: Add a new scope for a subnet enabled for NAP
```
PS C:\> Add-DhcpServerv4Scope -ComputerName dhcpserver.contoso.com -Name "Lab-5 Network" -StartRange 10.20.20.1 -EndRange 10.20.20.254 -SubnetMask 255.255.255.0 -State InActive -NapEnable
```

This example adds the specified inactive scope for 20.20.20.0/24 subnet on the DHCP server service.
The scope is enabled for NAP.

### Example 3: Add a new scope for a subnet as part of a superscope
```
PS C:\> Add-DhcpServerv4Scope -Name "Lab-6 Network" -StartRange 10.30.30.1 -EndRange 10.30.30.254 -SubnetMask 255.255.255.0 -SuperScope "Expanded Lab-6 Network"
```

This example adds a new scope for 10.30.30.0/24 subnet on the DHCP server service that runs on the local computer.
The scope is added as part of the superscope named Expanded Lab-6 Network.

## PARAMETERS

### -ActivatePolicies
Specifies the enabled state of the policy enforcement on the scope that is added.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: True
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -AsJob
Runs the cmdlet as a background job.
Use this parameter to run commands that take a long time to complete.
The cmdlet immediately returns an object that represents the job and then displays the command prompt.
You can continue to work in the session while the job completes.
To manage the job, use the `*-Job` cmdlets.
To get the job results, use the [Receive-Job](https://go.microsoft.com/fwlink/?LinkID=113372) cmdlet.
For more information about Windows PowerShell® background jobs, see [about_Jobs](https://go.microsoft.com/fwlink/?LinkID=113251).

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
Specifies the DNS name, or IPv4 or IPv6 address, of the target computer that runs the DHCP server service.

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

### -Delay
Specifies the number of milliseconds by which the DHCP server service should wait before responding to the client requests.
Specify this parameter if the scope is part of a split scope deployment and this DHCP server service should act as a secondary DHCP server service for the scope being added.

```yaml
Type: UInt16
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Description
Specifies the description string for the IPv4 scope that is added.

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

### -EndRange
Specifies the ending IP address of the range in the subnet from which IP addresses should be leased by the DHCP server service.

```yaml
Type: IPAddress
Parameter Sets: (All)
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -LeaseDuration
Specifies the time interval for which an IP address should be leased to a client in this scope.
This should be specified in the format `day.hrs:mins:secs`.

```yaml
Type: TimeSpan
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 8.00:00:00
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MaxBootpClients
Specifies, if the scope type is specified as Both to allow for both DHCP and BootP clients, the maximum number of BootP clients which should be leased an IP address from this scope.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the name of the IPv4 scope that is added.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NapEnable
Specifies the enabled state of Network Access Protection (NAP) for this scope.
If NAP is enabled, then the DHCP server service passes the statement of health (SoH) received from the client to the network policy server (NPS).
Based on the NAP profile set, the NPS determines the network access to grant to the client.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NapProfile
Specifies that the NAP profile should be set only if NAP is enabled on the scope.
The NAP profile refers to the MS Service Class which is a condition used in network policies on NPS.

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

### -StartRange
Specifies the starting IP address of the range in the subnet from which IP addresses should be leased by the DHCP server service.

```yaml
Type: IPAddress
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -State
Specifies the state of the scope when it is created.
The acceptable values for this parameter are: Active and Inactive.
Only an active scope responds to client requests.
The default value is Active.

```yaml
Type: String
Parameter Sets: (All)
Aliases:
Accepted values: Active, InActive

Required: False
Position: Named
Default value: Active
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SubnetMask
Specifies the subnet mask for the scope specified in IP address format.
For example: `255.255.255.0`.

```yaml
Type: IPAddress
Parameter Sets: (All)
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SuperscopeName
Specifies the name of the superscope to which the scope is added.

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
Specifies the type of clients to be serviced by the scope.
The acceptable values for this parameter are: DHCP, BootP, or Both.
The type of the scope determines whether the DHCP server service responds to only DHCP client requests, only BootP client requests, or Both types of clients.

```yaml
Type: String
Parameter Sets: (All)
Aliases:
Accepted values: Dhcp, Bootp, Both

Required: False
Position: Named
Default value: DHCP
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv4Scope
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv4Scope
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Get-DhcpServerv4Scope](./Get-DhcpServerv4Scope.md)

[Get-DhcpServerv4ScopeStatistics](./Get-DhcpServerv4ScopeStatistics.md)

[Remove-DhcpServerv4Scope](./Remove-DhcpServerv4Scope.md)

[Set-DhcpServerv4Scope](./Set-DhcpServerv4Scope.md)

