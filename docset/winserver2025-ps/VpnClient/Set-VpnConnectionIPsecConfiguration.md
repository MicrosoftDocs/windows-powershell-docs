---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_VpnConnectionIPsecConfiguration_v1.0.cdxml-help.xml
Module Name: VpnClient
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/vpnclient/set-vpnconnectionipsecconfiguration?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-VpnConnectionIPsecConfiguration
---

# Set-VpnConnectionIPsecConfiguration

## SYNOPSIS
Sets the IPsec parameters of a VPN connection.

## SYNTAX

### Default
```
Set-VpnConnectionIPsecConfiguration [-ConnectionName] <String> [-Force] [-AllUserConnection] [-RevertToDefault]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### CustomPolicy
```
Set-VpnConnectionIPsecConfiguration [-ConnectionName] <String>
 [-AuthenticationTransformConstants] <AuthenticationTransformConstants>
 [-CipherTransformConstants] <CipherTransformConstants> [-EncryptionMethod] <EncryptionMethod>
 [-IntegrityCheckMethod] <IntegrityCheckMethod> [-PfsGroup] <PfsGroup> [-DHGroup] <DHGroup> [-PassThru]
 [-Force] [-AllUserConnection] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-VpnConnectionIpsecConfiguration** cmdlet sets the IPsec parameters of a VPN connection.
The settings apply only to IKEv2 and L2TP VPN connections.

## EXAMPLES

### Example 1: Set the IPsec configuration for an IKEv2 tunnel
```
PS C:\> Add-VpnConnection -Name "Contoso" -ServerAddress 176.16.1.2 -TunnelType "Ikev2"
PS C:\> Set-VpnConnectionIPsecConfiguration -ConnectionName "Contoso" -AuthenticationTransformConstants None -CipherTransformConstants AES256 -EncryptionMethod AES256 -IntegrityCheckMethod SHA384 -PfsGroup None -DHGroup ECP384 -PassThru -Force
AuthenticationTransformConstants : None

CipherTransformConstants         : AES256

DHGroup                          : ECP384

IntegrityCheckMethod             : SHA384

PfsGroup                         : None

EncryptionMethod                 : AES256
```

This example sets the IPsec configuration for a VPN connection using IKEv2.

The first command uses the Add-VpnConnection cmdlet to add a VPN connection on the server with the address 176.16.1.2.
The cmdlet specifies an IKEv2 tunnel.

The second command uses the **Set-VpnConnectionIPsecConfiguration** cmdlet to set the configuration by using the *ConnectionName* parameter.
The command also specifies values for the *CipherTransformConstants*, *EncryptionMethod*, *IntegrityCheckMethod*, and *DHGroup* parameters.

### Example 2: Set the IPsec configuration for an L2TP tunnel
```
PS C:\> Add-VpnConnection -Name "Contoso" -ServerAddress 176.16.1.2 -TunnelType "L2tp"
PS C:\> Set-VpnConnectionIPsecConfiguration -ConnectionName "Contoso" -AuthenticationTransformConstants None -CipherTransformConstants AES128 -EncryptionMethod AES128 -IntegrityCheckMethod SHA256 -PfsGroup None -DHGroup ECP256 -PassThru -Force
AuthenticationTransformConstants : None

CipherTransformConstants         : AES128

DHGroup                          : ECP256

IntegrityCheckMethod             : SHA256

PfsGroup                         : None

EncryptionMethod                 : AES128
```

This example sets the IPsec configuration for an L2TP tunnel.

The first command uses **Add-VpnConnection** to add a VPN connection on the server with the address 176.16.1.2.
The command also specifies an L2TP tunnel.

The second command uses **Set-VpnConnectionIPsecConfiguration** to set the configuration.
The command also specifies values for the *CipherTransformConstants*, *EncryptionMethod*, *IntegrityCheckMethod*, and *DHGroup* parameters.

### Example 3: Set the IPsec configuration for an IKEv2 tunnel with 128-bit data blocks
```
PS C:\>Add-VpnConnection -Name "Contoso" -ServerAddress 176.16.1.2 -TunnelType "Ikev2"
PS C:\> Set-VpnConnectionIPsecConfiguration -ConnectionName "Contoso" -AuthenticationTransformConstants GCMAES128 -CipherTransformConstants None -EncryptionMethod AES128 -IntegrityCheckMethod SHA256 -PfsGroup None -DHGroup ECP256 -PassThru -Force
AuthenticationTransformConstants : GCMAES128

CipherTransformConstants         : None

DHGroup                          : ECP256

IntegrityCheckMethod             : SHA256

PfsGroup                         : None

EncryptionMethod                 : AES128
```

This example sets the IPsec configuration for an IKEv2 tunnel with authentication transform constants.

The first command uses *Add-VpnConnection* to add a VPN connection on the server with the address 176.16.1.2.
The cmdlet specifies an IKEv2 tunnel.

The second command uses **Set-VpnConnectionIPsecConfiguration** to set the configuration.
The command also specifies values for the *CipherTransformConstants*, *EncryptionMethod*, *IntegrityCheckMethod*, and *DHGroup* parameters, as well as specifying a value for the *AuthenticationTransformConstants* parameter.

### Example 4: Set the IPsec configuration for an IKEv2 tunnel with 256-bit data blocks
```
PS C:\>Add-VpnConnection -Name "Contoso" -ServerAddress 176.16.1.2 -TunnelType "Ikev2"
PS C:\> Set-VpnConnectionIPsecConfiguration -ConnectionName "Contoso" -AuthenticationTransformConstants GCMAES256 -CipherTransformConstants None -EncryptionMethod AES256 -IntegrityCheckMethod SHA384 -PfsGroup None -DHGroup ECP384 -PassThru -Force
AuthenticationTransformConstants : GCMAES256

CipherTransformConstants         : None

DHGroup                          : ECP384

IntegrityCheckMethod             : SHA384

PfsGroup                         : None

EncryptionMethod                 : AES256
```

This example sets the IPsec configuration for an IKEv2 tunnel, and specifies authentication transform constants.

The first command uses **Add-VpnConnection** to add a VPN connection on the server with the address 176.16.1.2.
The cmdlet specifies an IKEv2 tunnel.

The second command uses **Set-VpnConnectionIPsecConfiguration** to set the configuration.
The command also specifies values for the *CipherTransformConstants*, *EncryptionMethod*, *IntegrityCheckMethod*, and *DHGroup* parameters, as well as specifying a value for the *AuthenticationTransformConstants* parameter.

## PARAMETERS

### -AllUserConnection
Indicates that the VPN connection being modified is in the global phone book.

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
Specifies authentication header (AH) transform in the IPsec policy.
For more information, see the Set-VpnServerIPsecConfiguration cmdlet.
The acceptable values for this parameter are:

- MD596
- SHA196
- SHA256128
- GCMAES128
- GCMAES192
- GCMAES256
- None

```yaml
Type: AuthenticationTransformConstants
Parameter Sets: CustomPolicy
Aliases:
Accepted values: MD596, SHA196, SHA256128, GCMAES128, GCMAES192, GCMAES256, None

Required: True
Position: 2
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
Specifies Encapsulating Security Payload (ESP) cipher transform in the IPsec policy.
Acceptable values for this parameter are:

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
Aliases:
Accepted values: DES, DES3, AES128, AES192, AES256, GCMAES128, GCMAES192, GCMAES256, None

Required: True
Position: 3
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

### -ConnectionName
Specifies the name of a VPN connection profile to modify.
To view existing VPN connection profiles, use the Get-VpnConnection cmdlet.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Name

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DHGroup
Specifies the Diffie-Hellman (DH) Group to use during IKE key exchanges.
The acceptable values for this parameter are:

- None
- Group1
- Group2
- Group14
- ECP256
- ECP384
- Group24

```yaml
Type: DHGroup
Parameter Sets: CustomPolicy
Aliases:
Accepted values: None, Group1, Group2, Group14, ECP256, ECP384, Group24

Required: True
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EncryptionMethod
Specifies the encryption method.
The acceptable values for this parameter are:

- DES
- DES3
- AES128
- AES192
- AES256
- GCMAES128
- GCMAES256

```yaml
Type: EncryptionMethod
Parameter Sets: CustomPolicy
Aliases:
Accepted values: DES, DES3, AES128, AES192, AES256, GCMAES128, GCMAES256

Required: True
Position: 5
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Force
Forces the command to run without asking for user confirmation.

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

### -IntegrityCheckMethod
Specifies the integrity check method used to protect data from tampering.
The acceptable values for this parameter are:

- MD5
- SHA1
- SHA256
- SHA384

```yaml
Type: IntegrityCheckMethod
Parameter Sets: CustomPolicy
Aliases:
Accepted values: MD5, SHA1, SHA256, SHA384

Required: True
Position: 6
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru
Returns an object representing the item with which you are working.
By default, this cmdlet does not generate any output.
If you specify this parameter, the cmdlet returns the **VpnConnection** object that contains the **VpnConnection** configuration settings.

```yaml
Type: SwitchParameter
Parameter Sets: CustomPolicy
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PfsGroup
Specifies the Perfect Forwarding Secrecy (PFS) Group in the IPsec policy.
The acceptable values for this parameter are:

- None
- PFS1
- PFS2
- PFS2048
- ECP256
- ECP384
- PFSMM
- PFS24

```yaml
Type: PfsGroup
Parameter Sets: CustomPolicy
Aliases:
Accepted values: None, PFS1, PFS2, PFS2048, ECP256, ECP384, PFSMM, PFS24

Required: True
Position: 7
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RevertToDefault
Indicates that the cmdlet sets the IPsec parameters to the default values.

```yaml
Type: SwitchParameter
Parameter Sets: Default
Aliases:

Required: True
Position: 2
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

### Microsoft.Management.Infrastructure.CimInstance#VpnConnectionIPsecConfiguration

## NOTES

## RELATED LINKS

[Add-VpnConnection](./Add-VpnConnection.md)

