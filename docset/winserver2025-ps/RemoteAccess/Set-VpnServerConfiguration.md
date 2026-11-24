---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_VpnServerIPsecConfiguration_v1.0.0.cdxml-help.xml
Module Name: RemoteAccess
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/remoteaccess/set-vpnserverconfiguration?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-VpnServerConfiguration
---

# Set-VpnServerConfiguration

## SYNOPSIS
Updates S2S server parameters.

## SYNTAX

### EncryptionType (Default)
```
Set-VpnServerConfiguration [-TunnelType <TunnelType>] [-SstpPorts <UInt32>] [-GrePorts <UInt32>]
 [-IdleDisconnectSeconds <UInt32>] [-SALifeTimeSeconds <UInt32>] [-MMSALifeTimeSeconds <UInt32>]
 [-SADataSizeForRenegotiationKilobytes <UInt32>] [-Ikev2Ports <UInt32>] [-L2tpPorts <UInt32>] [-PassThru]
 [-EncryptionType <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### RevertToDefault
```
Set-VpnServerConfiguration [-TunnelType <TunnelType>] [-PassThru] [-RevertToDefault]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### CustomPolicy
```
Set-VpnServerConfiguration [-TunnelType <TunnelType>] [-SstpPorts <UInt32>] [-GrePorts <UInt32>]
 [-IdleDisconnectSeconds <UInt32>] [-SALifeTimeSeconds <UInt32>] [-MMSALifeTimeSeconds <UInt32>]
 [-SADataSizeForRenegotiationKilobytes <UInt32>] [-Ikev2Ports <UInt32>] [-L2tpPorts <UInt32>] [-PassThru]
 [-CustomPolicy] [-EncryptionMethod <EncryptionMethod>] [-IntegrityCheckMethod <IntegrityCheckMethod>]
 [-CipherTransformConstants <CipherTransformConstants>] [-PfsGroup <PfsGroup>]
 [-AuthenticationTransformConstants <AuthenticationTransformConstants>] [-DHGroup <DHGroup>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-VpnServerConfiguration** cmdlet updates IPSEC properties on RRAS server for incoming S2S VPN Interfaces.
By Specifying CustomPolicy, IPsec parameters can be customized.

## EXAMPLES

### Example 1: Change the idle disconnect time
```
PS C:\>Set-VpnServerConfiguration -IdleDisconnectSeconds 1000 -PassThru

```

This command changes the idle disconnect time of the VPN server to 1000 seconds. The command includes the PassThru parameter, so it sends a VpnServerIPsecConfiguration object to the console.

### Example 2: Configure a custom IPsec policy
```
PS C:\>Set-VpnServerConfiguration -CustomPolicy -EncryptionMethod "AES128" -DhGroup "Group2" -PfsGroup "PFS2" -CipherTransformConstants "AES128"  -IntegrityCheckMethod "SHA256" -AuthenticationTransformConstants "SHA256128" -PassThru

```

This command configures a custom IPsec policy for incoming VPN connections and S2S protocol VPN connections that do not use a pre-shared key as an authentication method.

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

### -AuthenticationTransformConstants
Specifies the authentication transform plumbed in Ipsec policy.

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

### -CipherTransformConstants
Specifies the cipher plumbed in IPsec policy.

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
Indicates the custom IKE IPSEC policy.

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
Specifies the DH Group Plumbed in Ipsec policy.

```yaml
Type: DHGroup
Parameter Sets: CustomPolicy
Aliases:
Accepted values: None, Group1, Group2, Group14, ECP256, ECP384, Group24

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EncryptionMethod
Specifies the encryption method plumbed in IKE policy.

```yaml
Type: EncryptionMethod
Parameter Sets: CustomPolicy
Aliases: Encryption
Accepted values: DES, DES3, AES128, AES192, AES256, GCMAES128, GCMAES256

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EncryptionType
Specifies the type of Encryption.

```yaml
Type: String
Parameter Sets: EncryptionType
Aliases:
Accepted values: NoEncryption, RequireEncryption, OptionalEncryption, MaximumEncryption

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -GrePorts
Specifies the number of Generic Routing Encapsulation (GRE) ports.

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

### -IdleDisconnectSeconds
Specifies the time, in seconds, after which an idle connection is terminated.
Unless the idle time-out is disabled, the entire connection is terminated if the connection is idle for the specified interval.

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
Specifies the number of IKEv2 ports that are created.

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
Specifies the integrity method plumbed in IPsec policy.

```yaml
Type: IntegrityCheckMethod
Parameter Sets: CustomPolicy
Aliases: FirstIntegrityAlgorithm, OtherHashAlgorithm
Accepted values: MD5, SHA1, SHA256, SHA384

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -L2tpPorts
Specifies the number of L2TP ports that are created.

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

### -MMSALifeTimeSeconds
Specifies the lifetime of a Main Mode security association (SA) in seconds, after which the SA is no longer valid.

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
Specifies the PFS Group plumbed in Ipsec policy.

```yaml
Type: PfsGroup
Parameter Sets: CustomPolicy
Aliases: PfsGroupId
Accepted values: None, PFS1, PFS2, PFS2048, ECP256, ECP384, PFSMM, PFS24

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RevertToDefault
Indicates that the IPsec parameters revert to a default value

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
Specifies the number of kilobytes that are allowed to transfer using a security association (SA), after which the SA will be renegotiated.

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
Specifies the lifetime of a SA in seconds, after which the SA is no longer valid.

```yaml
Type: UInt32
Parameter Sets: EncryptionType, CustomPolicy
Aliases: LifeTimeSeconds, QMSALifeTimeSeconds

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SstpPorts
Specifies the number of SSTP ports.

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
Specifies the maximum number of concurrent connections that can be established to run this command.
If you omit this parameter or enter a value of 0, the default value, 32, is used.

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
Specifies the Tunnel Type to which Custom Policy is to be applied

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.PowerShell.Cmdletization.GeneratedTypes.VpnServerIPsecConfiguration.TunnelType

### System.UInt32

### Microsoft.PowerShell.Cmdletization.GeneratedTypes.VpnServerIPsecConfiguration.EncryptionMethod

### Microsoft.PowerShell.Cmdletization.GeneratedTypes.VpnServerIPsecConfiguration.IntegrityCheckMethod

### Microsoft.PowerShell.Cmdletization.GeneratedTypes.VpnServerIPsecConfiguration.CipherTransformConstants

### Microsoft.PowerShell.Cmdletization.GeneratedTypes.VpnServerIPsecConfiguration.PfsGroup

### Microsoft.PowerShell.Cmdletization.GeneratedTypes.VpnServerIPsecConfiguration.AuthenticationTransformConstants

### Microsoft.PowerShell.Cmdletization.GeneratedTypes.VpnServerIPsecConfiguration.DHGroup

### System.String

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance

### Microsoft.Management.Infrastructure.CimInstance#VpnServerIPsecConfiguration

## NOTES

## RELATED LINKS

[Get-VpnServerConfiguration](./Get-VpnServerConfiguration.md)

