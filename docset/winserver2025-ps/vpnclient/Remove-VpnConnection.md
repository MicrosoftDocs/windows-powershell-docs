---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_VpnConnection_v1.0.0.cdxml-help.xml
Module Name: VpnClient
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/vpnclient/remove-vpnconnection?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-VpnConnection
---

# Remove-VpnConnection

## SYNOPSIS
Removes specified VPN connection profiles.

## SYNTAX

```
Remove-VpnConnection [-Name] <String[]> [-Force] [-PassThru] [-AllUserConnection] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-VpnConnection** cmdlet removes one or more specified VPN connection profiles.
If errors occur when you remove the VPN profile, or if the specified VPN profile does not exist, the error information is returned.

## EXAMPLES

### Example 1: Remove a single VPN connection
```
PS C:\> Remove-VpnConnection -Name "Test1" -Force -PassThru
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
```

This command removes the VPN connection named Test1.
The *Force* parameter suppresses warnings and non-terminating errors.

By specifying the *PassThru* parameter, you can see the configuration of the VPN connection object.

### Example 2: Remove multiple VPN connections
```
PS C:\>Remove-VpnConnection -Name "Test3",  "Test4",  "Test5" -AllUserConnection -Force -PassThru
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
```

This command removes the VPN connections named Test3, Test4 and Test5.
By specifying the *AllUserConnection* parameter, the connections are removed from the global phone book.
The *Force* parameter suppresses warnings and non-terminating errors.

By specifying the *PassThru* parameter, you can see the configuration of all of the VPN connection objects.

## PARAMETERS

### -AllUserConnection
Indicates that the VPN connection is removed from the global phone book.

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

### -Force
Forces the removal of the VPN profile from the phone book.

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

### -Name
Specifies the name of the VPN connection profile.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: ConnectionName

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
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

### Microsoft.Management.Infrastructure.CimInstance#VpnConnection[]
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

This cmdlet returns a **VpnConnection** object that contains the VPN Connection configuration settings.

## NOTES

## RELATED LINKS

[Add-VpnConnection](./Add-VpnConnection.md)

[Get-VpnConnection](./Get-VpnConnection.md)

[Set-VpnConnection](./Set-VpnConnection.md)

[New-EapConfiguration](./New-EapConfiguration.md)

