---
external help file: VpnClient_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: 7AC7839A-38B7-46F9-AC6D-55E522C4F112
manager: dansimp
---

# New-EapConfiguration

## SYNOPSIS
Generates a new XML file with the specified EAP configuration.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
New-EapConfiguration [-UseWinlogonCredential] [-AsJob] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
New-EapConfiguration [-Peap] [-VerifyServerIdentity] [[-TunneledEapAuthMethod] <XmlDocument>] [-AsJob]
 [-CimSession <CimSession[]>] [-EnableNap] [-FastReconnect <Boolean>] [-ThrottleLimit <Int32>] [-Confirm]
 [-WhatIf]
```

### UNNAMED_PARAMETER_SET_3
```
New-EapConfiguration [-Ttls] [-AsJob] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [[-TunneledEapAuthMethod] <XmlDocument>] [-TunneledNonEapAuthMethod <String>] [-UseWinlogonCredential]
 [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_4
```
New-EapConfiguration [-Tls] [-VerifyServerIdentity] [-AsJob] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-UserCertificate] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **New-EapConfiguration** cmdlet creates an XML file with the specified EAP configuration.
You use this cmdlet to create the EAP XML configuration file for EAP authentication that is then used by the Set-VpnConnection cmdlet or the Add-VpnConnection cmdlet.
If errors happen during the generation of the XML file, the error information is returned.

## EXAMPLES

### Example 1: Create a default EAP configuration object
```
PS C:\> $a = New-EapConfiguration
```

This command creates a default EAP configuration object, and stores it in the variable named $a.
You can use the XML configuration object stored in the variable when you create a VPN connection or change the configuration of a VPN connection.

### Example 2: Create a customized EAP configuration object
```
PS C:\> $a = New-EapConfiguration -UseWinlogonCredential
```

This command creates an EAP configuration object, customized by the **UseWinlogonCredential** parameter, and stores it in the variable named $a.
By specifying the **UseWinlogonCredential** parameter, the EAP configuration object is configured to use MSCHAPv2 as the authentication method, and that Windows logon credentials are used automatically when connecting with the VPN connection profile.

### Example 3: Create a TLS customized EAP configuration object
```
PS C:\> $a = New-EapConfiguration -Tls -VerifyServerIdentity -UserCertificate
```

This command creates a customized EAP configuration object and stores it in the variable named $a.
The EAP configuration object is customized by specifying the following parameters: 

- The **Tls** parameter, which indicates that this configuration object uses EAP-TLS
- The **VerifyServerIdentity** parameter, which indicates that the identity of the server to which the client connects is validated
- The **UserCertificate** parameter, which indicates that the EAP-TLS authentication method uses a user certificate.

### Example 4: Create a TTLS customized EAP configuration object
```
PS C:\> $a = New-EapConfiguration -Ttls
```

This command creates an EAP configuration object, customized by the **Ttls** parameter to use the TTLS authentication method.
The configuration object is stored in the variable named $a.

### Example 5: Create a TTLS EAP configuration object with MSCHAPv2 as the client authentication method
```
PS C:\> $a = New-EapConfiguration -Ttls -TunneledNonEapAuthMethod MSChapv2 -UseWinlogonCredential
```

This command creates a new EAP configuration object and stores it in the variable named $a.
The EAP configuration object is customized by specifying the following parameters: 

- The **Ttls** parameter, which indicates that this configuration object uses TTLS as the authentication method
- The **TunneledNonEapAuthMethod** parameter with the MSChapv2 value, which specifies that MSCHAPv2 is used as the specific client authentication method
- The **UseWinlogonCredential** parameter, which indicates that Windows logon credentials are used automatically when connecting with the VPN connection profile that uses this EAP configuration object.

### Example 6: Create an EAP configuration object and use it as input
```
This command creates an EAP configuration object configured to use an EAP-TLS authentication method and to verify the server identity. The configuration object is stored in a variable named $b.
PS C:\>$b = New-EapConfiguration -Tls -VerifyServerIdentity

This command creates an EAP configuration object configured to use the TTLS authentication method, and specifies the **TunneledEapAuthMethod** parameter to use the EapConfigXmlStream created by the first EAP configuration object as the tunnel EAP authentication method.
PS C:\>$a = New-EapConfiguration -Ttls -TunneledEapAuthMethod $b.EapConfigXmlStream
```

This set of commands creates an EAP configuration object customized with a TTLS authentication method which uses EAP-TLS as the tunneled client authentication method.

### Example 7: Create an EAP configuration object that uses PEAP authentication
```
PS C:\> $a = New-EapConfiguration -Peap
```

This command creates an EAP configuration object customized by the **PEAP** parameter to use the PEAP authentication method.
The configuration object is stored in a variable named $a.

### Example 8: Create a customized EAP configuration object and use it as input
```
This command creates the EAP configuration object and stores it in the variable named $b. The EAP configuration object is customized to use the TLS authentication method by the **Tls** parameter, and configured to verify the identity of the server by the **VerifyServerIdentity** parameter.This command implicitly configures a smart card to be used for authentication.
PS C:\>$b = New-EapConfiguration -Tls -VerifyServerIdentity

This command uses the EapConfigXmlStream of the EAP configuration object created in the previous command to specify the value for the TunneledEapAuthMethod parameter. This command also specifies that PEAP is the authentication method, as specified by the **Peap** parameter; that NAP is enabled for PEAP, as specified by the **EnableNap** parameter; and that **FastReconnect** is enabled, as specified by the **FastReconnect** parameter. 
PS C:\>$a = New-EapConfiguration -Peap -EnableNap -FastReconnect $true -VerifyServerIdentity -TunneledEapAuthMethod $b.EapConfigXmlStream
```

This set of commands creates an EAP configuration object customized with the TLS authentication method, and then uses its EapConfigXmlStream object as the tunneled authentication method.

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

### -EnableNap
Indicates that Network Access Protection (NAP) is enabled for PEAP.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -FastReconnect
Specifies whether FastReconnect is enabled or disabled in the current PEAP configuration.
Specify either `$true` or `$false`.

```yaml
Type: Boolean
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: Named
Default value: True
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Peap
Indicates that PEAP is used as the authentication method.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
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

### -Tls
Indicates that EAP-TLS, either smart card based or user certificate based, is used as the authentication method.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_4
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Ttls
Indicates that TTLS is used as the authentication method.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TunneledEapAuthMethod
Specifies the configuration XML for tunneled EAP, EAP-TTLS, or PEAP authentication.

```yaml
Type: XmlDocument
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: 4
Default value: None
Accept pipeline input: True (ByValue, ByPropertyName)
Accept wildcard characters: False
```

```yaml
Type: XmlDocument
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: 

Required: False
Position: 4
Default value: None
Accept pipeline input: True (ByValue, ByPropertyName)
Accept wildcard characters: False
```

### -TunneledNonEapAuthMethod
Specifies the simple EAP-TTLS client authentication methods.
The acceptable values for this parameter are:**Pap**, **Chap**, **MSChap**, and **MSCHapv2**.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: 

Required: False
Position: Named
Default value: Pap
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -UserCertificate
Indicates that a user certificate is used for authentication. 
This parameter is used with EAP-TLS.
If this parameter is not specified, a smart card authentication is used.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_4
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -UseWinlogonCredential
Indicates that MSCHAPv2 or EAP-MSCHAPv2 is used as the authentication method, and that Windows logon credentials are used automatically when connecting with the VPN connection profile.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: 

Required: False
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VerifyServerIdentity
Indicates that server identity validation is performed for the VPN connection. 
This parameter is used with PEAP, and EAP-TLS with tunneled EAP client authentication.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_2, UNNAMED_PARAMETER_SET_4
Aliases: 

Required: False
Position: 3
Default value: False
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

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/RemoteAccess/ClientEapConfiguration
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.
                         
The VpnConnection object contains the VpnConnection configuration settings.

## NOTES

## RELATED LINKS



