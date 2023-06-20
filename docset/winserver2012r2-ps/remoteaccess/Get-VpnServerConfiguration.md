---
external help file: PS_VpnServerIPsecConfiguration_v1.0.0.cdxml-help.xml
Module Name: RemoteAccess
ms.date: 12/05/2017
online version: https://learn.microsoft.com/powershell/module/remoteaccess/get-vpnserverconfiguration?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-VpnServerConfiguration
---

# Get-VpnServerConfiguration

## SYNOPSIS
Gets VPN server properties.

## SYNTAX

```
Get-VpnServerConfiguration [-TunnelType <TunnelType>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-VpnServerConfiguration** cmdlet gets virtual private network (VPN) server properties.
The cmdlet gets settings for a Routing and Remote Access service (RRAS) server for incoming server-to-server protocol (S2S protocol) VPN interfaces.
You can restrict the type of tunnel to view by specifying the **TunnelType** parameter.

## EXAMPLES

### Example 1: Display IPsec properties
```
PS C:\> Get-VpnServerIPsecConfiguration
EncryptionType                 : OptionalEncryption

Ikev2Ports                     : 5

SstpPorts                      : 10

IdleDisconnect(s)              : 300

L2tpPorts                      : 5

SADataSizeForRenegotiation(KB) : 102400

SALifeTime(s)                  : 28800
```

This command displays properties for the current VPN server.

## PARAMETERS

### -AsJob
ps_cimcommon_asjob

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
Enter a computer name or a session object, such as the output of a New-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227967 or Get-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227966 cmdlet.
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

### -TunnelType
Specifies a tunnel type.
If you specify a value for this parameter, the cmdlet gets properties only for tunnels of that type.
The acceptable values for this parameter are:

- PPTP.
Point-to-Point Tunneling Protocol.
- L2TP.
Layer Two Tunneling Protocol.
- SSTP.
Secure Socket Tunneling Protocol.
- IKEv2.
Internet Key Exchange version 2.
- Automatic.

```yaml
Type: TunnelType
Parameter Sets: (All)
Aliases: 
Accepted values: IKEV2, L2TP

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#VpnServerIPsecConfiguration

## NOTES

## RELATED LINKS

[Set-VpnServerConfiguration](./Set-VpnServerConfiguration.md)

