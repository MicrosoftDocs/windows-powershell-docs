---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_VPNIPAddressAssignment_v1.0.0.cdxml-help.xml
Module Name: RemoteAccess
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/remoteaccess/set-vpnipaddressassignment?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-VpnIPAddressAssignment
---

# Set-VpnIPAddressAssignment

## SYNOPSIS
Configures the IPv4 address assignment method or the IPv6 prefix for IPv6 address assignment.

## SYNTAX

### VpnIPAddressAssignment (Default)
```
Set-VpnIPAddressAssignment [-IPAddressRange <String[]>] [-ComputerName <String>] [-IPAssignmentMethod <String>]
 [-IPv6Prefix <String>] [-PassThru] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### VpnIPv6PrefixEntrypoint
```
Set-VpnIPAddressAssignment [-ComputerName <String>] -IPv6Prefix <String> [-PassThru] -EntrypointName <String>
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-VpnIPAddressAssignment** cmdlet is only used to toggle from one IPv4 address assignment type to another.
This cmdlet cannot be used to add additional IPv4 address ranges if a static pool IP address assignment is being used.

 -- This cmdlet cannot be used to Enable or Disable an IPv4 or IPv6 address assignment.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Set-VpnIPAddressAssignment -IPAssignmentMethod "Dhcp" -PassThru
IPAssignmentMethod : Dhcp
IPAddressRangeList :
IPv6Prefix         :
```

This cmdlet sets the IPv4 address assignment type to be DHCP which causes IPv4 address assignment to happen from a DHCP server.

### EXAMPLE 2
```
PS C:\>Set-VpnIPAddressAssignment -IPAssignmentMethod "StaticPool" -IPAddressRange "30.1.1.10", "30.1.1.30" -IPv6Prefix "2002:836b:2:1000::/64" -PassThru
WARNING: The remoteaccess service must be restarted for the changes to take effect.

IPAssignmentMethod : StaticPool
IPAddressRangeList : {30.1.1.10 - 30.1.1.30}
IPv6Prefix         : 2002:836b:2:1000::/64
```

The cmdlet specifies the IPv4 address assignment to happen from the IP range 30.1.1.10 through 30.1.1.30.
IPv6 prefix 2002:836b:2:1000::/64 is used for IPv6 address assignment.
Changing the IPv6 prefix requires the remote access service to be restarted in order to take effect.
This is conveyed through the warning message.

## PARAMETERS

### -AsJob
Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to complete.

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
Specifies the IPv4 or IPv6 address, or host name, of the computer on which the VPN server computer specific tasks should be run.
If this parameter is specified, then the address assignment properties are configured for that VPN server.

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

### -EntrypointName
Specifies a site in a multi-site deployment for which the IPv6 prefix needs to be configured.
This parameter is not applicable to the IPv4 address assignment properties as these properties are always configured at the individual server level and not site level.

If this parameter is not specified in a multi-site deployment, then this parameter value to which the cmdlet is run is used.
The server could also be represented by using the **ComputerName** parameter.

If this parameter and the **ComputerName** parameter are specified and the **ComputerName** does not belong to the site represented by this parameter, then this parameter takes precedence and the authentication type is configured for it.

```yaml
Type: String
Parameter Sets: VpnIPv6PrefixEntrypoint
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IPAddressRange
Specifies the IP address range from which IP addresses are allocated to VPN clients.
Consists of a starting IP and an ending IP.
This parameter can be configured only if the **IPAssignmentMethod** parameter is specified to be StaticPool.

If there are no pre-existing IPv4 address pools, then it is mandatory to specify an address range.

```yaml
Type: String[]
Parameter Sets: VpnIPAddressAssignment
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IPAssignmentMethod
Specifies the mechanism for IPv4 address assignment.
The acceptable values for this parameter are:

 -- Dhcp.

 -- StaticPool.

When load balancing is active the IPv4 address assignment method cannot be configured to DHCP.
Only a static pool is supported.

```yaml
Type: String
Parameter Sets: VpnIPAddressAssignment
Aliases:
Accepted values: Dhcp, StaticPool

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IPv6Prefix
Specifies the IPv6 prefix used for IPv6 address assignment.

```yaml
Type: String
Parameter Sets: VpnIPAddressAssignment
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: VpnIPv6PrefixEntrypoint
Aliases:

Required: True
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

### System.String[]

### System.String

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance

### Microsoft.Management.Infrastructure.CimInstance#VpnIPAddressAssignment

The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

The object consists of the following properties:

 -- The IPv4 assignment method configured:  DHCP or static pool.

 -- If static pool assignment is configured for IPv4, then the list of configured address pools.
Each pool consists of a starting IP address and an ending IP address.

 -- The IPv6 prefix configured.

## NOTES

## RELATED LINKS

[Add-VpnIPAddressRange](./Add-VpnIPAddressRange.md)

[Remove-VpnIPAddressRange](./Remove-VpnIPAddressRange.md)

