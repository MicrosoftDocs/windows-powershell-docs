---
external help file: NetTransition_Cmdlets.xml
Module Name: NetworkTransition
online version: https://learn.microsoft.com/powershell/module/networktransition/new-netiphttpsconfiguration?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# New-NetIPHttpsConfiguration

## SYNOPSIS
Creates an IP-HTTPS configuration.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
New-NetIPHttpsConfiguration [-PolicyStore] <String> [-AsJob] [-AuthMode <AuthMode>]
 [-CimSession <CimSession[]>] [-Profile <String>] [-State <State>] [-StrongCRLRequired <Boolean>]
 [-ThrottleLimit <Int32>] [-Type <Type>] -ServerURL <String> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
New-NetIPHttpsConfiguration [-GPOSession] <String> [-AsJob] [-AuthMode <AuthMode>] [-CimSession <CimSession[]>]
 [-Profile <String>] [-State <State>] [-StrongCRLRequired <Boolean>] [-ThrottleLimit <Int32>] [-Type <Type>]
 -ServerURL <String> [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **New-NetIPHttpsConfiguration** cmdlet creates an IP-HTTPS configuration.

This cmdlet can create IP-HTTPS configurations on the ActiveStore, PersistentStore, or Group Policy Objects (GPOs).

## EXAMPLES

### Example 1: Create an IP-HTTPS configuration
```
PS C:\>New-NetIPHttpsConfiguration -Profile "Redmond" -ServerURL "https://contoso.com:443/IPHTTPs" -PolicyStore "Domain\TestGPO"
```

This command creates an IP-HTTPS configuration named Redmond with the specified server URL https://contoso.com:443/IPHTTPs in the GPO named TestGPO.

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

### -AuthMode
Specifies the authentication mode of the IP-HTTPS configuration. 
The acceptable values for this parameter are:

 -- None: Performs no client authentication during the SSL handshake.
This is the default value. 

 -- Certificates: Uses client certificates to authenticate clients.
This authentication mode applies only to a server interface on a computer running Windows Server® 2012.

```yaml
Type: AuthMode
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

### -GPOSession
Specifies the Group Policy session in which to store the configuration information. 

You can use this parameter with the **NetGPO** cmdlets to aggregate multiple operations performed on a GPO. 

You cannot use this parameter with the **PolicyStore** parameter.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PolicyStore
Specifies the policy store to which to add the configuration profile. 
The acceptable values for this parameter are:

 -- ActiveStore 

 -- PersistentStore 

 -- GPO 

To add the configuration profile to a GPO, specify the GPO name using the following format: `Domain\GPOName`

You cannot use this parameter with the **GPOSession** parameter.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Profile
Specifies the name by which to identify the IP-HTTPS configuration profile.
This option is only available if the store is a GPO.

```yaml
Type: String
Parameter Sets: (All)
Aliases: IPHttpsProfile

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServerURL
Specifies the URL for the server.
If the profile is a client profile, Windows Server 2012 attempts to connect to the server URL.
If the profile is a server profile, then this is the URL on which the server listens. 
                         
Specify the server URL using the following format: https://myserver/IPHTTPS

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -State
Specifies the state behavior of IP-HTTPS. 
The acceptable values for this parameter are:

 -- Default: 

 ---- For a server interface, IP-HTTPS is always configured. 

 ---- For a client interface, IP-HTTPS is configured on-demand based on the other connectivity options available.
Client interfaces are created with this setting by default. 

 -- Enabled: IP-HTTPS is always configured, for both server interfaces and client interfaces.
Server interfaces are created with this setting by default. 

 -- Disabled: Disables the IP-HTTPS interface. 

 -- OutsideEnabled: IP-HTTPs is configured on-demand whenever the computer is outside of the corporate network.

```yaml
Type: State
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: Default
Accept pipeline input: False
Accept wildcard characters: False
```

### -StrongCRLRequired
Indicates if a strong certificate revocation list (CRL) check is required before a connection. 

By default, the value of this parameter is False.

```yaml
Type: Boolean
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

### -Type
Specifies if IP-HTTPS should start in server mode or client mode.
Server mode is only allowed on Windows Server 2012.

```yaml
Type: Type
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
This cmdlet accepts no input objects.

## OUTPUTS

### System.Object
This cmdlet returns an object.

## NOTES

## RELATED LINKS

[Get-NetIPHttpsConfiguration](./Get-NetIPHttpsConfiguration.md)

[Remove-NetIPHttpsConfiguration](./Remove-NetIPHttpsConfiguration.md)

[Rename-NetIPHttpsConfiguration](./Rename-NetIPHttpsConfiguration.md)

[Reset-NetIPHttpsConfiguration](./Reset-NetIPHttpsConfiguration.md)

[Set-NetIPHttpsConfiguration](./Set-NetIPHttpsConfiguration.md)

