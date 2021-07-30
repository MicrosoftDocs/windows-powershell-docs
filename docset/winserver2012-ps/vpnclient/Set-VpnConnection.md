---
external help file: VpnClient_Cmdlets.xml
Module Name: VpnClient
online version: https://docs.microsoft.com/powershell/module/vpnclient/set-vpnconnection?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-VpnConnection

## SYNOPSIS
Changes the configuration settings of an existing VPN connection profile.

## SYNTAX

```
Set-VpnConnection [[-RememberCredential] <Boolean>] [[-UseWinlogonCredential] <Boolean>]
 [[-EapConfigXmlStream] <XmlDocument>] [-Name] <String> [[-ServerAddress] <String>] [[-TunnelType] <String>]
 [[-EncryptionLevel] <String>] [[-AuthenticationMethod] <String[]>] [[-SplitTunneling] <Boolean>]
 [-AllUserConnection] [[-L2tpPsk] <String>] [-AsJob] [-CimSession <CimSession[]>] [-Force] [-PassThru]
 [-ThrottleLimit <Int32>] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Set-VpnConnection** cmdlet changes the configuration settings of an existing VPN connection profile. 
If the VPN profile specified does not exist, you see an error. 
If errors occur when you modify the VPN profile, the error information is returned.

## EXAMPLES

### Example 1: Configure a single VPN connection
```
PS C:\> Set-VpnConnection -Name "Test1" -ServerAddress "10.1.1.2" -PassThru
Name                  : Test1

ServerAddress         : 10.1.1.2

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

This command configures the VPN connection named Test1 to connect to the server with an IP address of 10.1.1.2.
By specifying the **Passthru** parameter, you can see the configuration of the VPN connection object.

### Example 2:
```
PS C:\>Set-VpnConnection -Name "Test3" -AllUserConnection -TunnelType L2tp -EncryptionLevel Optional -AuthenticationMethod Pap -SplitTunneling:$false -RememberCredential:$false -PassThru

WARNING: The currently selected encryption level requires EAP or MS-CHAPv2 logon security methods. Data encryption will not occur for Pap or Chap.

Name                  : Test3

ServerAddress         : 10.1.1.1

AllUserConnection     : True

Guid                  : {76746D4E-D72A-467D-A11F-3D4D9075F50D}

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
```

This command configures the VPN connection named Test3 and located in the global phone book as follows: 

- The connection is configured to use L2tp as the tunnel type, as specified by the **TunnelType** parameter 
- The tunnel is using optional encryption, as specified by the **EncryptionLevel** parameter 
- The authentication method used by the connection is PAP, as specified by the **AuthenticationMethod** parameter 
- Split tunneling is turned off, as specified by the **SplitTunneling** parameter, and the value of `$false`
- Credential caching is turned off, as specified by the **RememberCredential** parameter and the value of  `$false`

By specifying the **Passthru** parameter, you can see the configuration of the VPN connection object.

### Example 3: Configure a VPN connection to use a custom EAP configuration
```
This command stores the result of the New-EapConfiguration cmdlet into the variable named $a.
PS C:\>$a = New-EapConfiguration -Tls


This command configures the VPN connection named Test4 in the global phone book to use the custom EAP configuration by: 

-- Specifying the **AuthenticationMethod** parameter with the value EAP
-- Specifying the **EapConfigXmlStream** parameter with the value of the **EapConfigXmlStream** method of the previously created variable.By specifying the **Passthru** parameter, you can see the configuration of the VPN connection object.
PS C:\>Set-VpnConnection -Name "Test4" -AllUserConnection -AuthenticationMethod Eap -EapConfigXmlStream $a.EapConfigXmlStream -PassThru

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

This set of commands first creates a custom EAP configuration, and then configures a VPN connection from the global phone book to use the new custom EAP configuration.

For more information about custom EAP creation, see the New-EapConfiguration cmdlet.

## PARAMETERS

### -AllUserConnection
Indicates that the VPN connection specified is in the global phone book.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: 8
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

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

### -AuthenticationMethod
Specifies the authentication method to use for the VPN connection.
The acceptable values for this parameter are:**PAP**, **CHAP**, **MSCHAPv2**, or **EAP**.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 6
Default value: MSChapv2
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a New-CimSessionhttps://go.microsoft.com/fwlink/p/?LinkId=227967 or Get-CimSessionhttps://go.microsoft.com/fwlink/p/?LinkId=227966 cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EapConfigXmlStream
Specifies the contents of the EAP XML configuration file, which includes the EAP method identifier (ID).

```yaml
Type: XmlDocument
Parameter Sets: (All)
Aliases: 

Required: False
Position: 12
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EncryptionLevel
Specifies the encryption level for the VPN connection.
The acceptable values for this parameter are:**NoEncryption**, **Optional**, **Required** and **Maximum**.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 5
Default value: Required
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Force
Indicates that the pre-shared key (PSK) value is be supplied over an insecure channel, if L2TP is used,

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

### -L2tpPsk
Specifies the value of the PSK to be used for L2TP authentication.
If this parameter is not specified, a certificate is used for L2TP.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 9
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the name of the VPN connection profile.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
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

### -RememberCredential
Indicates that the credentials supplied at the time of first successful connection is stored in the cache, if set to `$true`..

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: 10
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
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SplitTunneling
Indicates that split tunneling is enabled for the VPN connection profile, if set to `$true`

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: 7
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
The acceptable values for this parameter are:**PPTP**, **L2TP**, **SSTP**, **IKEv2**, or **Automatic**.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 4
Default value: Automatic
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -UseWinlogonCredential
Indicates that MSCHAPv2 or EAP-MSCHAPv2 is used as the authentication method, and that Windows logon credentials are used automatically when connecting with the VPN connection profile, if set to `$true`

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: 11
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#VpnConnection
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

The VpnConnection object contains the VpnConnection configuration settings.

## NOTES

## RELATED LINKS

[Add-VpnConnection](./Add-VpnConnection.md)

[Get-VpnConnection](./Get-VpnConnection.md)

[Remove-VpnConnection](./Remove-VpnConnection.md)

