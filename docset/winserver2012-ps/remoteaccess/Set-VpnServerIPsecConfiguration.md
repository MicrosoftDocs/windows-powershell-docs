---
external help file: UnifiedRA_Cmdlets.xml
Module Name: RemoteAccess
online version: https://learn.microsoft.com/powershell/module/remoteaccess/set-vpnserveripsecconfiguration?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-VpnServerIPsecConfiguration

## SYNOPSIS
Sets the IPsec parameters for a site-to-site (S2S) server.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Set-VpnServerIPsecConfiguration [-AsJob] [-CimSession <CimSession[]>] [-EncryptionType <String>]
 [-IdleDisconnectSeconds <UInt32>] [-Ikev2Ports <UInt32>] [-L2tpPorts <UInt32>] [-PassThru]
 [-SADataSizeForRenegotiationKilobytes <UInt32>] [-SALifeTimeSeconds <UInt32>] [-ThrottleLimit <Int32>]
 [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Set-VpnServerIPsecConfiguration [-AsJob] [-AuthenticationTransformConstants <AuthenticationTransformConstants>]
 [-CimSession <CimSession[]>] [-CipherTransformConstants <CipherTransformConstants>] [-DHGroup <DHGroup>]
 [-EncryptionMethod <EncryptionMethod>] [-IdleDisconnectSeconds <UInt32>] [-Ikev2Ports <UInt32>]
 [-IntegrityCheckMethod <IntegrityCheckMethod>] [-L2tpPorts <UInt32>] [-PassThru] [-PfsGroup <PfsGroup>]
 [-SADataSizeForRenegotiationKilobytes <UInt32>] [-SALifeTimeSeconds <UInt32>] [-ThrottleLimit <Int32>]
 [-CustomPolicy] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Set-VpnServerIPsecConfiguration** cmdlet configures IPsec properties on Routing and Remote Access (RRAS) server for incoming site-to-site (S2S) VPN interfaces.
If the **CustomPolicy** parameter is specified, then IPsec parameters can be customized.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Set-VpnServerIPsecConfiguration -IdleDisconnectSeconds 1000 -PassThru
WARNING: Configuration parameters will be modified after the Remote Access service is restarted. 
 
EncryptionType                 : OptionalEncryption 
Ikev2Ports                     : 5 
IdleDisconnect(s)              : 1000 
L2tpPorts                      : 5 
SADataSizeForRenegotiation(KB) : 102400 
SALifeTime(s)                  : 28800
```

This example modifies the number of seconds to idle before disconnecting for the VPN server.

### EXAMPLE 2
```
PS C:\>Set-VpnServerIPsecConfiguration -CustomPolicy -EncryptionMethod "AES128" -DhGroup "Group2" -PfsGroup "PFS2" -CipherTransformConstants "AES128" -IntegrityCheckMethod "SHA256" -AuthenticationTransformConstants "SHA256128" -PassThru
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

This example sets a custom IPsec policy for incoming VPN connections and S2S VPN connections for which the authentication method is not PSK.

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
Specifies the authentication transform in the IPsec policy.

```yaml
Type: AuthenticationTransformConstants
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: Named
Default value: 2
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
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CipherTransformConstants
Specifies the cipher in the IPsec policy.

```yaml
Type: CipherTransformConstants
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: Named
Default value: 1
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CustomPolicy
Specifies the custom IKE IPsec policies.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DHGroup
Specifies the Diffie-Hellman (DH) group in the IPsec policy.

```yaml
Type: DHGroup
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: Named
Default value: 2
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EncryptionMethod
Specifies the encryption method in the IKE policy.

```yaml
Type: EncryptionMethod
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: Named
Default value: 4
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EncryptionType
Specifies the type of encryption.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: OptionalEncryption
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IdleDisconnectSeconds
Specifies the time, in seconds, after which an idle connection is disconnected.
Unless the idle time-out is Disabled, the entire connection is disconnected if the connection is idle for the specified interval.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: 300
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Ikev2Ports
Specifies the number of IKEv2 ports to create.

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

### -IntegrityCheckMethod
Specifies the integrity method in the IPsec policy.

```yaml
Type: IntegrityCheckMethod
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: Named
Default value: 2
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -L2tpPorts
Specifies the number of L2TP ports to create.

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
Specifies the perfect forward secrecy (PFS) group in the IPsec policy.

```yaml
Type: PfsGroup
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: Named
Default value: 3
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SADataSizeForRenegotiationKilobytes
Specifies the number of kilobytes that are allowed to transfer using a security association (SA).
After that the SA will be renegotiated.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: 10000
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SALifeTimeSeconds
Specifies the lifetime of a SA in seconds, after which the SA is no longer valid.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: 7200
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

### None

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#VpnServerIPsecConfiguration
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Add-VpnS2SInterface](./Add-VpnS2SInterface.md)

[Clear-VpnS2SInterfaceStatistics](./Clear-VpnS2SInterfaceStatistics.md)

[Connect-VpnS2SInterface](./Connect-VpnS2SInterface.md)

[Disconnect-VpnS2SInterface](./Disconnect-VpnS2SInterface.md)

[Get-VpnAuthProtocol](./Get-VpnAuthProtocol.md)

[Get-VpnS2SInterface](./Get-VpnS2SInterface.md)

[Get-VpnS2SInterfaceStatistics](./Get-VpnS2SInterfaceStatistics.md)

[Get-VpnServerIPsecConfiguration](./Get-VpnServerIPsecConfiguration.md)

[Remove-VpnS2SInterface](./Remove-VpnS2SInterface.md)

[Set-VpnAuthProtocol](./Set-VpnAuthProtocol.md)

[Set-VpnS2SInterface](./Set-VpnS2SInterface.md)

