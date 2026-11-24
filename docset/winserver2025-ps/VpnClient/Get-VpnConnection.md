---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_VpnConnection_v1.0.0.cdxml-help.xml
Module Name: VpnClient
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/vpnclient/get-vpnconnection?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-VpnConnection
---

# Get-VpnConnection

## SYNOPSIS
Retrieves the specified VPN connection profile information.

## SYNTAX

```
Get-VpnConnection [[-Name] <String[]>] [-AllUserConnection] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-VpnConnection** cmdlet retrieves the specified VPN connection profile and its properties.
If you do not specify a profile name, the cmdlet returns a list of all VPN connections in the phone book.

## EXAMPLES

### Example 1: Get all available VPN connections
```
PS C:\> Get-VpnConnection
Name                  : Test1
ServerAddress         : 10.1.1.2
AllUserConnection     : False
Guid                  : {65EA2A6D-60A5-49DA-AEDF-5542171D3794}
TunnelType            : Automatic
AuthenticationMethod  : {MsChapv2}
EncryptionLevel       : Required
L2tpIPsecAuth         : Certificate
UseWinlogonCredential : False
EapConfigXmlStream    :
ConnectionStatus      : Disconnected
NapState              : NotConnected
RememberCredential    : False
SplitTunneling        : False
DnsSuffix             :
IdleDisconnectSeconds : 0

Name                  : Test6
ServerAddress         : 10.1.1.1
AllUserConnection     : False
Guid                  : {03D226D4-3EBF-4B67-9618-4E310AD3FE87}
TunnelType            : Ikev2
AuthenticationMethod  : {MachineCertificate}
EncryptionLevel       : Required
L2tpIPsecAuth         :
UseWinlogonCredential : False
EapConfigXmlStream    :
ConnectionStatus      : Disconnected
NapState              : NotConnected
RememberCredential    : False
SplitTunneling        : False
DnsSuffix             :
IdleDisconnectSeconds : 0

Name                  : Test7
ServerAddress         : Washington
AllUserConnection     : False
Guid                  : {671F26F9-7C5C-44B2-8271-BD2005FCE702}
TunnelType            : Automatic
AuthenticationMethod  : {MsChapv2}
EncryptionLevel       : Required
L2tpIPsecAuth         : Certificate
UseWinlogonCredential : False
EapConfigXmlStream    :
ConnectionStatus      : Disconnected
NapState              : NotConnected
RememberCredential    : False
SplitTunneling        : False
DnsSuffix             :
IdleDisconnectSeconds : 0
```

This command returns a list of all available VPN connections in the user's local phone book.

### Example 2: Get all available VPN connections from the global phonebook
```
PS C:\>Get-VpnConnection -AllUserConnection
Name                  : Test5
ServerAddress         : 10.1.1.1
AllUserConnection     : True
Guid                  : {CF59A4C3-57DB-41FA-9793-D0C785756ABD}
TunnelType            : L2tp
AuthenticationMethod  : {Eap}
EncryptionLevel       : Required
L2tpIPsecAuth         : Certificate
UseWinlogonCredential : False
EapConfigXmlStream    : #document
ConnectionStatus      : Disconnected
NapState              : NotConnected
RememberCredential    : True
SplitTunneling        : True
DnsSuffix             :
IdleDisconnectSeconds : 0

Name                  : Test3
ServerAddress         : 10.1.1.1
AllUserConnection     : True
Guid                  : {E37453AF-EE0B-4DD8-9AC0-30B262B0CA74}
TunnelType            : L2tp
AuthenticationMethod  : {Pap}
EncryptionLevel       : Optional
L2tpIPsecAuth         : Certificate
UseWinlogonCredential : False
EapConfigXmlStream    :
ConnectionStatus      : Disconnected
NapState              : NotConnected
RememberCredential    : False
SplitTunneling        : False
DnsSuffix             : washington.contoso.com
IdleDisconnectSeconds : 600

Name                  : Test4
ServerAddress         : 10.1.1.1
AllUserConnection     : True
Guid                  : {C5D5579E-FF9D-4F31-ABE1-B26AB38107CD}
TunnelType            : L2tp
AuthenticationMethod  : {Eap}
EncryptionLevel       : Required
L2tpIPsecAuth         : Psk
UseWinlogonCredential : False
EapConfigXmlStream    : #document
ConnectionStatus      : Disconnected
NapState              : NotConnected
RememberCredential    : True
SplitTunneling        : True
DnsSuffix             :
IdleDisconnectSeconds : 0
```

This command retrieves all the available VPN connections from the global phone book.

### Example 3: Get a specific VPN connection from the global phone book
```
PS C:\>Get-VpnConnection -Name "Test3" -AllUserConnection
Name                  : Test3
ServerAddress         : 10.1.1.1
AllUserConnection     : True
Guid                  : {E37453AF-EE0B-4DD8-9AC0-30B262B0CA74}
TunnelType            : L2tp
AuthenticationMethod  : {Pap}
EncryptionLevel       : Optional
L2tpIPsecAuth         : Certificate
UseWinlogonCredential : False
EapConfigXmlStream    :
ConnectionStatus      : Disconnected
NapState              : NotConnected
RememberCredential    : False
SplitTunneling        : False
DnsSuffix             : washington.contoso.com
IdleDisconnectSeconds : 600
```

This command retrieves the VPN connection named Test3 from the global phone book.

### Example 4: Get multiple VPN connections
```
PS C:\>Get-VpnConnection -Name "Test3", "Test4", "test5" -AllUserConnection
Name                  : Test3
ServerAddress         : 10.1.1.1
AllUserConnection     : True
Guid                  : {E37453AF-EE0B-4DD8-9AC0-30B262B0CA74}
TunnelType            : L2tp
AuthenticationMethod  : {Pap}
EncryptionLevel       : Optional
L2tpIPsecAuth         : Certificate
UseWinlogonCredential : False
EapConfigXmlStream    :
ConnectionStatus      : Disconnected
NapState              : NotConnected
RememberCredential    : False
SplitTunneling        : False
DnsSuffix             : washington.contoso.com
IdleDisconnectSeconds : 600

Name                  : Test4
ServerAddress         : 10.1.1.1
AllUserConnection     : True
Guid                  : {C5D5579E-FF9D-4F31-ABE1-B26AB38107CD}
TunnelType            : L2tp
AuthenticationMethod  : {Eap}
EncryptionLevel       : Required
L2tpIPsecAuth         : Psk
UseWinlogonCredential : False
EapConfigXmlStream    : #document
ConnectionStatus      : Disconnected
NapState              : NotConnected
RememberCredential    : True
SplitTunneling        : True
DnsSuffix             :
IdleDisconnectSeconds : 0

Name                  : test5
ServerAddress         : 10.1.1.1
AllUserConnection     : True
Guid                  : {CF59A4C3-57DB-41FA-9793-D0C785756ABD}
TunnelType            : L2tp
AuthenticationMethod  : {Eap}
EncryptionLevel       : Required
L2tpIPsecAuth         : Certificate
UseWinlogonCredential : False
EapConfigXmlStream    : #document
ConnectionStatus      : Disconnected
NapState              : NotConnected
RememberCredential    : True
SplitTunneling        : True
DnsSuffix             :
IdleDisconnectSeconds : 0
```

This command retrieves multiple specified VPN connections from the global phone book.

## PARAMETERS

### -AllUserConnection
Indicates that the VPN connection is retrieved from the global phone book.

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

### -Name
Specifies an array of names of VPN connection profiles.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: ConnectionName

Required: False
Position: 1
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

### Microsoft.Management.Infrastructure.CimInstance#VpnConnection[]
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

This cmdlet returns a **VpnConnection** object that contains the VPN connection configuration settings.

## NOTES

## RELATED LINKS

[Add-VpnConnection](./Add-VpnConnection.md)

[Set-VpnConnection](./Set-VpnConnection.md)

[Remove-VpnConnection](./Remove-VpnConnection.md)

[New-EapConfiguration](./New-EapConfiguration.md)

