---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_VpnTrafficselector_v1.0.cdxml-help.xml
Module Name: RemoteAccess
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/remoteaccess/new-vpntrafficselector?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-VpnTrafficSelector
---

# New-VpnTrafficSelector

## SYNOPSIS
Creates a VPN Traffic selector object that configures the IKE traffic selector.

## SYNTAX

```
New-VpnTrafficSelector [[-IPAddressRange] <String[]>] [[-PortRange] <UInt32[]>] [-ProtocolId <UInt32>]
 [-Type <Type>] [-TsPayloadId <UInt16>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## DESCRIPTION
The **New-VpnTrafficSelector** cmdlet creates a virtual private network (VPN) traffic selector object that is used to configure the Internet Key Exchange (IKEv2) VPN traffic selectors.

## EXAMPLES

### Example 1: Create two IKEv2 VPN traffic selectors and configure them for an S2S VPN interface
```
PS C:\>$LocalTS  = New-VpnTrafficSelector -IPAddressRange 10.10.0.0, 10.10.255.255 -PortRange 100, 1000 -Protocol 6 -Type IPv4
PS C:\> $RemoteTS = New-VpnTrafficSelector -IPAddressRange 20.20.0.0, 20.20.255.255 -PortRange 100, 1000 -Protocol 6 -Type IPv4
PS C:\> Set-VpnS2SInterface -Name EDGE1 -LocalVpnTrafficSelector $LocalTS -RemoteVpnTrafficSelector $RemoteTS
```

This command creates two IKEv2 VPN traffic selectors and then configures them for a S2S VPN Interface.

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

### -IPAddressRange
Specifies a sting array that contains the address range allowed in the traffic selector.

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

### -PortRange
Specifies the port range allowed in the traffic selector.

```yaml
Type: UInt32[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ProtocolId
Specifies the protocol ID allowed for the traffic selector.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit
Specifies the maximum number of concurrent connections that can be established to run this command.
If you omit this parameter or enter a value of 0, the default value, 32, is used.

The throttle limit applies only to the current command, not to the session or to the computer.

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

### -TsPayloadId
{{Fill TsPayloadId Description}}

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

### -Type
Specifies an enumeration to specify address family (IPv4 or IPv6) in the address range.
Acceptable values for this enumeration are:

- IPv4
- IPv6

```yaml
Type: Type
Parameter Sets: (All)
Aliases:
Accepted values: IPv4, IPv6

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String[]

### System.UInt32[]

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance

### Microsoft.Management.Infrastructure.CimInstance#VpnTrafficSelector

## NOTES

## RELATED LINKS

[Remote Access Cmdlets](./remoteaccess.md)

