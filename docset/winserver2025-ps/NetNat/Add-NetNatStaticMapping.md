---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_NetNatStaticMapping.cdxml-help.xml
Module Name: NetNat
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/netnat/add-netnatstaticmapping?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-NetNatStaticMapping
---

# Add-NetNatStaticMapping

## SYNOPSIS
Adds a static mapping to a NAT instance.

## SYNTAX

```
Add-NetNatStaticMapping [-NatName] <String> -Protocol <Protocol> [-RemoteExternalIPAddressPrefix <String>]
 -ExternalIPAddress <String> -ExternalPort <UInt16> -InternalIPAddress <String> [-InternalPort <UInt16>]
 [-InternalRoutingDomainId <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Add-NetNatStaticMapping** cmdlet adds a static mapping to a network address translation (NAT) instance.
A static mapping enables an incoming connection from an external network to access a host on an internal network through the NAT.

You can use NAT to share a connection to the public Internet through a single interface with a single public IP address.
The computers on the private network use private, non-routable addresses.
NAT maps the private addresses to the public address.

## EXAMPLES

### Example 1: Add a static mapping to a NAT instance
```
PS C:\> Add-NetNatStaticMapping -ExternalIPAddress "a.b.c.0/24" -ExternalPort 80 -InternalIPAddress "192.0.02.179" -InternalPort 8080 -InternalRoutingDomainId "{12345678-0000-0000-0000-123456789012}"
```

This command adds a static mapping to a NAT instance.
The command specifies that NAT maps the external IP address to the internal IP address 192.0.02.179.
The command specifies that the NAT maps the destination port 80 of the Internet resource to the source application port 8080.
The command specifies that the tenant compartment that has the ID TSQATenant contains the internal address and internal port.
This example uses the placeholder a.b.c.0/24 to represent a public Internet address prefix.

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

### -ExternalIPAddress
Specifies the external IP address to which an incoming connection is addressed.
This parameter specifies the destination IP address in the incoming packet.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExternalPort
Specifies the external port to which an incoming connection is sent.
This parameter specifies the destination port in the incoming TCP or UDP packets.

```yaml
Type: UInt16
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InternalIPAddress
Specifies the IP address to which the packets from a remote machine in the external network are addressed.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InternalPort
Specifies the internal port to which the packets from a remote machine in the external network are sent.
If you do not specify this parameter, NAT uses the port that you specify for the *ExternalPort* parameter for the internal port.

```yaml
Type: UInt16
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InternalRoutingDomainId
Specifies the GUID of the routing domain of the internal interface.

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

### -NatName
Specifies the name of the NAT instance.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Protocol
Specifies the network protocol of the client computer in the internal network.
The acceptable values for this parameter are:

- TCP
- UDP

```yaml
Type: Protocol
Parameter Sets: (All)
Aliases:
Accepted values: TCP, UDP

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemoteExternalIPAddressPrefix
Specifies the IP address prefix of the remote computer on the external network.

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

### None

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/StandardCimv2/MSFT_NetNatStaticMapping

## NOTES

## RELATED LINKS

[Get-NetNatStaticMapping](./Get-NetNatStaticMapping.md)

[Remove-NetNatStaticMapping](./Remove-NetNatStaticMapping.md)

