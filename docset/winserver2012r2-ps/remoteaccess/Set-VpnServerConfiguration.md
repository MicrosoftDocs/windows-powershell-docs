---
external help file: PS_VpnServerIPsecConfiguration_v1.0.0.cdxml-help.xml
online version: 
schema: 2.0.0
title: Set-VpnServerConfiguration
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/05/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: B3270D2C-2E5A-490C-9176-292B1586BD4E
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Set-VpnServerConfiguration

## SYNOPSIS
Configures VPN server properties.

## SYNTAX

### EncryptionType (Default)
```
Set-VpnServerConfiguration [-TunnelType <TunnelType>] [-SstpPorts <UInt32>] [-IdleDisconnectSeconds <UInt32>]
 [-SALifeTimeSeconds <UInt32>] [-SADataSizeForRenegotiationKilobytes <UInt32>] [-Ikev2Ports <UInt32>]
 [-L2tpPorts <UInt32>] [-PassThru] [-EncryptionType <String>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### RevertToDefault
```
Set-VpnServerConfiguration [-TunnelType <TunnelType>] [-PassThru] [-RevertToDefault]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### CustomPolicy
```
Set-VpnServerConfiguration [-TunnelType <TunnelType>] [-SstpPorts <UInt32>] [-IdleDisconnectSeconds <UInt32>]
 [-SALifeTimeSeconds <UInt32>] [-SADataSizeForRenegotiationKilobytes <UInt32>] [-Ikev2Ports <UInt32>]
 [-L2tpPorts <UInt32>] [-PassThru] [-CustomPolicy] [-EncryptionMethod <EncryptionMethod>]
 [-IntegrityCheckMethod <IntegrityCheckMethod>] [-CipherTransformConstants <CipherTransformConstants>]
 [-PfsGroup <PfsGroup>] [-AuthenticationTransformConstants <AuthenticationTransformConstants>]
 [-DHGroup <DHGroup>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-VpnServerConfiguration** cmdlet configures virtual private network (VPN) server properties.
The cmdlet modifies settings for a Routing and Remote Access service (RRAS) server for incoming server-to-server protocol (S2S protocol) VPN interfaces.

You can configure the size and duration of a security association (SA), and specify an idle disconnect time.

Specify an encryption type by using the **EncryptionType** parameter

Create a custom policy by specifying the **CustomPolicy** parameter.
You can specify a tunnel type and how many ports to create for different tunnel types.
You can also specify cipher transform constants, Diffie-Hellman (DH) group, encryption method, integrity method, and perfect forward secrecy (PFS) group.

Change the settings back to default values by using the **RevertToDefault** parameter.

## EXAMPLES

### Example 1: Change the idle disconnect time
```
PS C:\>Set-VpnServerConfiguration -IdleDisconnectSeconds 1000 -PassThru
WARNING: Configuration parameters will be modified after the Remote Access service is restarted.
EncryptionType                 : OptionalEncryption

Ikev2Ports                     : 5

IdleDisconnect(s)              : 1000

L2tpPorts                      : 5

SADataSizeForRenegotiation(KB) : 102400

SALifeTime(s)                  : 28800
```

This command changes the idle disconnect time to 1000 seconds for the VPN server.
The command includes the **PassThru** parameter, so the command sends a **VpnServerIPsecConfiguration** object to the console.

### Example 2: Configure a custom IPsec policy
```
PS C:\> Set-VpnServerConfiguration -CustomPolicy -AuthenticationTransformConstants "SHA256128" -CipherTransformConstants "AES128" -DHhGroup "Group2" -EncryptionMethod "AES128" -IntegrityCheckMethod "SHA256" -PassThru -PfsGroup "PFS2"
WARNING: Configuration parameters will be modified after the Remote Access service is restarted.

AuthenticationTransformConstants : SHA256128

CipherTransformConstants         : AES128

CustomPolicy                     : True

DHGroup                          : Group2

EncryptionMethod                 : AES128

Ikev2Ports                       : 5

IdleDisconnect(s)                : 1000

IntegrityCheckMethod             : SHA256

L2tpPorts                        : 5

PFSgroup                         : PFS2

SADataSizeForRenegotiation(KB)   : 102400

SALifeTime(s)                    : 28800
```

This command configures a custom IPsec policy for incoming VPN connections and S2S protocol VPN connections that do not use a pre-shared key as an authentication method.

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

### -AuthenticationTransformConstants
Specifies authentication transform constants.
The acceptable values for this parameter are:

- SHA256128
- MD596
- SHA196
- GCMAES128
- GCMAES192
- GCMAES256
- None

```yaml
Type: AuthenticationTransformConstants
Parameter Sets: CustomPolicy
Aliases: FirstTransformType
Accepted values: MD596, SHA196, SHA256128, GCMAES128, GCMAES192, GCMAES256, None

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### -CipherTransformConstants
Specifies cipher transform constants.
The acceptable values for this parameter are:

- DES
- DES3
- AES128
- AES192
- AES256
- GCMAES128
- GCMAES192
- GCMAES256
- None

```yaml
Type: CipherTransformConstants
Parameter Sets: CustomPolicy
Aliases: FirstCipherAlgorithm, OtherCipherAlgorithm
Accepted values: DES, DES3, AES128, AES192, AES256, GCMAES128, GCMAES192, GCMAES256, None

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### -CustomPolicy
Indicates that the cmdlet sets custom Internet Key Exchange (IKE) Internet Protocol security (IPsec) policies.

```yaml
Type: SwitchParameter
Parameter Sets: CustomPolicy
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DHGroup
Specifies a DH group.
The server uses this value to generate IKE keys.
The acceptable values for this parameter are:

- Group1
- Group2
- Group14
- ECP256
- ECP384
- Group24
- None

```yaml
Type: DHGroup
Parameter Sets: CustomPolicy
Aliases: 
Accepted values: None, Group1, Group2, Group14, ECP256, ECP384, Group24

Required: False
Position: Named
Default value: 2
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EncryptionMethod
Specifies an encryption method.
The server uses this encryption method to generate IKE keys.
The acceptable values for this parameter are:

- DES
- DES3
- AES128
- AES192
- AES256

```yaml
Type: EncryptionMethod
Parameter Sets: CustomPolicy
Aliases: Encryption
Accepted values: DES, DES3, AES128, AES192, AES256

Required: False
Position: Named
Default value: 4
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EncryptionType
Specifies the type of encryption.
The acceptable values for this parameter are:

- NoEncryption
- RequireEncryption
- OptionalEncryption
- MaximumEncryption

```yaml
Type: String
Parameter Sets: EncryptionType
Aliases: 
Accepted values: NoEncryption, RequireEncryption, OptionalEncryption, MaximumEncryption

Required: False
Position: Named
Default value: OptionalEncryption
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IdleDisconnectSeconds
Specifies amount of time, in seconds, after which the server disconnects an idle connection.

```yaml
Type: UInt32
Parameter Sets: EncryptionType, CustomPolicy
Aliases: IdleDurationSeconds

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Ikev2Ports
Specifies the number of ports to create for IKE version 2.

```yaml
Type: UInt32
Parameter Sets: EncryptionType, CustomPolicy
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IntegrityCheckMethod
Specify the integrity check method for IPsec.
The acceptable values for this parameter are:

- MD5
- SHA1
- SHA256
- SHA384

```yaml
Type: IntegrityCheckMethod
Parameter Sets: CustomPolicy
Aliases: FirstIntegrityAlgorithm, OtherHashAlgorithm
Accepted values: MD5, SHA1, SHA256, SHA384

Required: False
Position: Named
Default value: 2
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -L2tpPorts
Specifies the number of ports to create for Layer Two Tunneling Protocol (L2TP).

```yaml
Type: UInt32
Parameter Sets: EncryptionType, CustomPolicy
Aliases: 

Required: False
Position: Named
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

### -PfsGroup
Specifies the PFS group.
The acceptable values for this parameter are:

- PFS1
- PFS2
- PFS2048
- ECP256
- ECP384
- PFSMM
- PFS24
- None

```yaml
Type: PfsGroup
Parameter Sets: CustomPolicy
Aliases: PfsGroupId
Accepted values: None, PFS1, PFS2, PFS2048, ECP256, ECP384, PFSMM, PFS24

Required: False
Position: Named
Default value: 3
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RevertToDefault
Indicates that the cmdlet sets IPsec properties to their default values.

```yaml
Type: SwitchParameter
Parameter Sets: RevertToDefault
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SADataSizeForRenegotiationKilobytes
Specifies the amount of data, in kilobytes, to transfer using a particular SA.
When data transfer reaches this limit, the server renegotiates the SA.

```yaml
Type: UInt32
Parameter Sets: EncryptionType, CustomPolicy
Aliases: LifeTimeKiloBytes

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SALifeTimeSeconds
Specifies the length of time, in seconds, of an SA.
After this interval, the SA becomes invalid.

```yaml
Type: UInt32
Parameter Sets: EncryptionType, CustomPolicy
Aliases: LifeTimeSeconds

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SstpPorts
Specifies the number of ports to create for Secure Socket Tunneling Protocol (SSTP).

```yaml
Type: UInt32
Parameter Sets: EncryptionType, CustomPolicy
Aliases: 

Required: False
Position: Named
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
Specifies a tunnel type.
The custom policy applies to this type of tunnel.
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#VpnServerIPsecConfiguration

## NOTES

## RELATED LINKS

[Get-VpnServerConfiguration](./Get-VpnServerConfiguration.md)

