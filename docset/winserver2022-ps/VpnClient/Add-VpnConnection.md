---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_VpnConnection_v1.0.0.cdxml-help.xml
Module Name: VpnClient
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/vpnclient/add-vpnconnection?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-VpnConnection
---

# Add-VpnConnection

## SYNOPSIS
Adds a VPN connection to the Connection Manager phone book.

## SYNTAX

### ThirdParty
```
Add-VpnConnection [-Name] <String> [-ServerAddress] <String> [-RememberCredential] [-SplitTunneling] [-Force]
 [-PassThru] [-ServerList <CimInstance[]>] [-DnsSuffix <String>] [-IdleDisconnectSeconds <UInt32>]
 [-PlugInApplicationID] <String> -CustomConfiguration <XmlDocument> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InboxProfile
```
Add-VpnConnection [-Name] <String> [-ServerAddress] <String> [[-TunnelType] <String>] [-AllUserConnection]
 [-RememberCredential] [-SplitTunneling] [-Force] [-PassThru] [[-L2tpPsk] <String>] [-UseWinlogonCredential]
 [-ServerList <CimInstance[]>] [-DnsSuffix <String>] [-IdleDisconnectSeconds <UInt32>]
 [[-EapConfigXmlStream] <XmlDocument>] [[-AuthenticationMethod] <String[]>] [[-EncryptionLevel] <String>]
 [-MachineCertificateIssuerFilter <X509Certificate2>] [-MachineCertificateEKUFilter <String[]>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Add-VpnConnection** cmdlet adds a VPN connection with the specified parameters to the Connection Manager phone book.
If errors occur when you create the VPN profile, the cmdlet returns the error information.

## EXAMPLES

### Example 1: Add a VPN connection
```powershell
PS C:\> Add-VpnConnection -Name "Test1" -ServerAddress "10.1.1.1" -PassThru
```
```output
Name                  : Test1
ServerAddress         : 10.1.1.1
AllUserConnection     : False 
Guid                  : {4B308E9B-C225-42CB-8158-307193429591}
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
```

This command adds a VPN connection named Test1 to the server with an IP address 10.1.1.1.
By specifying the *PassThru* parameter, you can see the configuration of the VPN connection object.

### Example 2: Add a VPN connection with an alternate authentication method
```powershell
PS C:\> Add-VpnConnection -Name "Test3" -ServerAddress "10.1.1.1" -TunnelType "Pptp" -EncryptionLevel "Required" -AuthenticationMethod MSChapv2 -UseWinlogonCredential -SplitTunneling -AllUserConnection -RememberCredential -PassThru
```
```output
Name                  : Test3 
ServerAddress         : 10.1.1.1 
AllUserConnection     : True 
Guid                  : {76746D4E-D72A-467D-A11F-3D4D9075F50D} 
TunnelType            : Pptp 
AuthenticationMethod  : {MsChapv2} 
EncryptionLevel       : Required 
L2tpIPsecAuth         : 
UseWinlogonCredential : True 
EapConfigXmlStream    : 
ConnectionStatus      : Disconnected 
NapState              : NotConnected 
RememberCredential    : True 
SplitTunneling        : True
```

This command adds a VPN connection named Test3 to the server with an IP address 10.1.1.1.
This connection uses the MSCHAPv2 authentication method, as specified by the **AuthenticationMethod** parameter.
Additional parameters specify that the connection: 

- Uses the Windows logon credentials (the **UseWinlogonCredential** parameter) 
- Uses split tunneling (the **SplitTunneling** parameter) 
- Is stored in the global phone book (the **AllUserConnection** parameter) 
- Caches the credentials used for the first successful connection (the **RememberCredential** parameter)

By specifying the **PassThru** parameter, you can see the configuration of the VPN connection object.

### Example 3: Add a VPN connection that uses EAP authentication
```powershell
PS C:\> Add-VpnConnection -Name "Test4" -ServerAddress "10.1.1.1" -TunnelType "L2tp" -EncryptionLevel "Required" -AuthenticationMethod Eap -SplitTunneling -AllUserConnection -L2tpPsk "password" -Force -RememberCredential -PassThru
```
```output
Name                  : Test4 
ServerAddress         : 10.1.1.1 
AllUserConnection     : True 
Guid                  : {1D423FF3-E3D4-404A-B052-DB9130656D29} 
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
```

This command adds a VPN connection named Test4 to the server with an IP address of 10.1.1.1.
This connection uses the default EAP authentication method, as specified by the **AuthenticationMethod** parameter.
The pre-shared key for the connection is specified by the **L2tpPsk** parameter. Additional parameters specify that the connection: 

- Uses split tunneling (the **SplitTunneling** parameter) 
- Is stored in the global phone book (the **AllUserConnection** parameter) 
- Caches the credentials used for the first successful connection (the **RememberCredential** parameter)

By specifying the **PassThru** parameter, you can see the configuration of the VPN connection object.

### Example 4: Add a VPN connection that uses a custom EAP authentication method
```powershell
PS C:\> $A = New-EapConfiguration
PS C:\> Add-VpnConnection -Name "Test5" -ServerAddress "10.1.1.1" -TunnelType "L2tp" -EncryptionLevel "Required" -AuthenticationMethod Eap -SplitTunneling -AllUserConnection -RememberCredential -EapConfigXmlStream $A.EapConfigXmlStream -PassThru
```
```output
Name                  : Test5 
ServerAddress         : 10.1.1.1 
AllUserConnection     : True 
Guid                  : {CF9F624F-D7DF-48BA-BD4B-D4E34AE05148} 
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
```

This set of commands adds a VPN connection using a custom EAP authentication method.
For more information about custom EAP authentication methods, see the **New-EapConfiguration** cmdlet.

### Example 5: Add a VPN connection that uses already generated EAP XML configuration
```powershell
PS C:\> $EAPXml = Get-Content -Path C:\eap-config.xml
PS C:\> Add-VpnConnection -Name "Test6" -ServerAddress "10.1.1.1" -TunnelType "L2tp" -EncryptionLevel "Required" -AuthenticationMethod Eap -SplitTunneling -AllUserConnection -RememberCredential -EapConfigXmlStream $EAPXml
```

This set of commands adds a VPN connection using an already generated EAP XML configuration. For more information about how to generate EAP XML configuration, see [EAP Configuration](/windows/client-management/mdm/eap-configuration).

## PARAMETERS

### -AllUserConnection
Indicates that the cmdlet adds the VPN connection to the global phone book entries.

```yaml
Type: SwitchParameter
Parameter Sets: InboxProfile
Aliases: 

Required: False
Position: 7
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

### -AuthenticationMethod
Specifies the authentication method to use for the VPN connection.

```yaml
Type: String[]
Parameter Sets: InboxProfile
Aliases: 
Accepted values: Pap, Chap, MSChapv2, Eap, MachineCertificate

Required: False
Position: 5
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### -CustomConfiguration
Specifies an XML document that allows vendors to specify custom configuration information.

```yaml
Type: XmlDocument
Parameter Sets: ThirdParty
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DnsSuffix
Specifies the DNS suffix of the VPN connection.

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

### -EapConfigXmlStream
Specifies the contents of the EAP XML configuration file, which includes the EAP method ID.

```yaml
Type: XmlDocument
Parameter Sets: InboxProfile
Aliases: 

Required: False
Position: 11
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EncryptionLevel
Specifies the encryption level for the VPN connection.

```yaml
Type: String
Parameter Sets: InboxProfile
Aliases: 
Accepted values: NoEncryption, Optional, Required, Maximum, Custom

Required: False
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Force
Indicates that the pre-shared key (PSK) value is supplied over an insecure channel, if L2TP is used.

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

### -IdleDisconnectSeconds
Specifies the time, in seconds, before an idle connection is closed.

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

### -L2tpPsk
Specifies the value of the PSK to be used for L2TP authentication.
If this parameter is not specified, a certificate is used for L2TP.

```yaml
Type: String
Parameter Sets: InboxProfile
Aliases: 

Required: False
Position: 8
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MachineCertificateEKUFilter
Specifies an array of enhanced key usage (EKU) filters for Internet Key Exchange version 2 (IKEv2) machine certificate selection.

```yaml
Type: String[]
Parameter Sets: InboxProfile
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MachineCertificateIssuerFilter
Specifies the X509 certificate of the issuer filter for IKEv2 machine certificate selection.

```yaml
Type: X509Certificate2
Parameter Sets: InboxProfile
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the name of this VPN connection profile.

```yaml
Type: String
Parameter Sets: (All)
Aliases: ConnectionName

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

### -PlugInApplicationID
Specifies the identifier for a third party application.

```yaml
Type: String
Parameter Sets: ThirdParty
Aliases: 

Required: True
Position: 10
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RememberCredential
Indicates that the credentials supplied at the time of first successful connection are stored in the cache.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: 9
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ServerAddress
Specifies the address of the remote VPN server to which the client connects.
You can specify the address as a URL, an IPv4 address, or an IPv6 address.

```yaml
Type: String
Parameter Sets: (All)
Aliases: ServerName, DefaultServer

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ServerList
Specifies an array of VPN servers.
The VPN client can connect to these servers.

```yaml
Type: CimInstance[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SplitTunneling
Indicates that the cmdlet enables split tunneling for this VPN connection profile.
When you enable split tunneling, traffic to destinations outside the intranet does not flow through the VPN tunnel.
If you do not specify this parameter, split tunneling is disabled.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: 6
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

### -TunnelType
Specifies the type of tunnel used for the VPN connection.

```yaml
Type: String
Parameter Sets: InboxProfile
Aliases: 
Accepted values: Pptp, L2tp, Sstp, Ikev2, Automatic

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -UseWinlogonCredential
Indicates that MSCHAPv2 or EAP MSCHAPv2 is used as the authentication method, and that Windows logon credentials are used automatically when connecting with this VPN connection profile.

```yaml
Type: SwitchParameter
Parameter Sets: InboxProfile
Aliases: 

Required: False
Position: 10
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

### CommonParameters
This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#VpnConnection
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

This cmdlet returns a **VpnConnection** object that contains the VPN connection configuration settings.

## NOTES

## RELATED LINKS

[Get-VpnConnection](./Get-VpnConnection.md)

[Set-VpnConnection](./Set-VpnConnection.md)

[Remove-VpnConnection](./Remove-VpnConnection.md)

[New-EapConfiguration](./New-EapConfiguration.md)
