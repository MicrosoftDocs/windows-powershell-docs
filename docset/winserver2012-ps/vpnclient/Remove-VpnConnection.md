---
external help file: VpnClient_Cmdlets.xml
Module Name: VpnClient
online version: https://docs.microsoft.com/powershell/module/vpnclient/remove-vpnconnection?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Remove-VpnConnection

## SYNOPSIS
Removes the specified VPN connection profile.

## SYNTAX

```
Remove-VpnConnection [-Name] <String[]> [-AllUserConnection] [-AsJob] [-CimSession <CimSession[]>] [-Force]
 [-PassThru] [-ThrottleLimit <Int32>] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Remove-VpnConnection** cmdlet removes one or more specified VPN connection profiles.
If errors occur when you remove the VPN profile, or if the specified VPN profile does not exist, the error information is returned.

## EXAMPLES

### Example 1: Removing a single VPN connection
```
PS C:\> Remove-VpnConnection -Name "Test1" -Force -PassThru
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

This command removes the VPN connection named Test1.
The **Force** parameter ensures that the connection is removed from the phone book.

By specifying the **Passthru** parameter, you can see the configuration of the VPN connection object.

### Example 2: Removing multiple VPN connections
```
PS C:\>Remove-VpnConnection -Name "Test3", "Test4", "Test5" -AllUserConnection -Force -PassThru

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

ServerAddress         : 1.1.1.3

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

This command removes the VPN connections named Test3, Test4 and Test5.
By specifying the **AllUserConnection** parameter, the connections are removed from the global phone book.
The **Force** parameter ensures that the connection is removed from the phone book.

By specifying the **Passthru** parameter, you can see the configuration of all of the VPN connection objects.

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
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByValue, ByPropertyName)
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

### Microsoft.Management.Infrastructure.CimInstance#VpnConnection[]
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

The VpnConnection object contains the VpnConnection configuration settings.

## NOTES

## RELATED LINKS

[Add-VpnConnection](./Add-VpnConnection.md)

[Get-VpnConnection](./Get-VpnConnection.md)

[Set-VpnConnection](./Set-VpnConnection.md)

[New-EapConfiguration](./New-EapConfiguration.md)

