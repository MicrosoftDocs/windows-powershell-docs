---
external help file: VpnClient_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: 61959313-33E4-4933-9083-A8F7A079F057
manager: dansimp
---

# Get-VpnConnection

## SYNOPSIS
Retrieves the specified VPN connection profile information.

## SYNTAX

```
Get-VpnConnection [[-Name] <String[]>] [-AllUserConnection] [-AsJob] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>]
```

## DESCRIPTION
The **Get-VpnConnection** cmdlet retrieves the specified VPN connection profile and its properties.
If you do not specify a profile name, the cmdlet returns a list of all VPN connections in the phone book.

## EXAMPLES

### Example 1: Get all available VPN connections
```
PS C:\> Get-VpnConnection
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

This command returns a list of all available VPN connections in the user's local phone book.

### Example 2: Get all available VPN connections from the global phonebook
```
PS C:\>Get-VpnConnection -AllUserConnection

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

Name                  : Test4 

ServerAddress         : 10.1.1.2 

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

Name                  : Test5 

ServerAddress         : 10.1.1.3
 
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

This command retrieves all the available VPN connections from the global phone book.

### Example 3: Get a specific VPN connection from the global phone book
```
PS C:\>Get-VpnConnection -Name "Test3" -AllUserConnection

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

This command retrieves the VPN connection named Test3 from the global phone book.

### Example 4: Get multiple VPN connections
```
PS C:\>Get-VpnConnection -Name "Test3", "Test4", "test5" -AllUserConnection

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

Name                  : Test4 

ServerAddress         : 10.1.1.2 

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

Name                  : test5 

ServerAddress         : 10.1.1.3 

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
Aliases: 

Required: False
Position: 2
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

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#VpnConnection[]
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

The VpnConnection object contains the VpnConnection configuration settings.

## NOTES

## RELATED LINKS

[Add-VpnConnection](./Add-VpnConnection.md)

[Set-VpnConnection](./Set-VpnConnection.md)

[Remove-VpnConnection](./Remove-VpnConnection.md)

[New-EapConfiguration](./New-EapConfiguration.md)

