---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_NetIpHTTPsConfiguration.cdxml-help.xml
Module Name: NetworkTransition
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/networktransition/set-netiphttpsconfiguration?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-NetIPHttpsConfiguration
---

# Set-NetIPHttpsConfiguration

## SYNOPSIS
Modifies an IP-HTTPS configuration.

## SYNTAX

### ByPolicyStore (Default)
```
Set-NetIPHttpsConfiguration [-Profile <String[]>] [-ProfileActivated <Boolean[]>] [-PolicyStore <String>]
 [-State <State>] [-Type <Type>] [-AuthMode <AuthMode>] [-StrongCRLRequired <Boolean>] [-ServerURL <String>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ByGpoSession
```
Set-NetIPHttpsConfiguration [-Profile <String[]>] [-ProfileActivated <Boolean[]>] [-GPOSession <String>]
 [-State <State>] [-Type <Type>] [-AuthMode <AuthMode>] [-StrongCRLRequired <Boolean>] [-ServerURL <String>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### InputObject (cdxml)
```
Set-NetIPHttpsConfiguration -InputObject <CimInstance[]> [-State <State>] [-Type <Type>] [-AuthMode <AuthMode>]
 [-StrongCRLRequired <Boolean>] [-ServerURL <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-NetIPHttpsConfiguration** cmdlet modifies an IP-HTTPS configuration.

You can specify the IP-HTTPS configuration profile to modify either by using a configuration object retrieved by the Get-NetIPHttpsConfiguration cmdlet or by specifying the profile name.

## EXAMPLES

### Example 1: Set the server URL of the profile
```
PS C:\>Set-NetIPHttpsConfiguration -Profile "Redmond" -ServerURL "https://da.com:443/IPHTTPs" -PolicyStore "Domain\TestGPO"
```

This command modifies the profile named Redmond in the GPO named TestGPO, modifying the server URL.

### Example 2: Set the server URL using IP-HTTPS configuration object
```
PS C:\>Get-NetIPHttpsConfiguration -Profile "Redmond" -PolicyStore "Domain\TestGPO" | Set-NetIPHttpsConfiguration -ServerURL "https://da.com:443/IPHTTPs"
```

This command gets the IP-HTTPS configuration profile named Redmond in the GPO named TestGPO using the Get-NetIPHttpsConfiguration cmdlet, and then provides the output object as input to this cmdlet using the pipeline operator.

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

### -AuthMode
Specifies the authentication mode.
The acceptable values for this parameter are:

- None.
Performs no client authentication during the SSL handshake.
This is the default value.
- Certificates.
Uses client certificates to authenticate clients.
This authentication mode applies only to a server interface on a computer running Windows Server® 2012 or Windows Server 2016.

```yaml
Type: AuthMode
Parameter Sets: (All)
Aliases:
Accepted values: None, Certificates

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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

### -GPOSession
Specifies the Group Policy session to which to store the configuration information.

You can use this parameter with the **NetGPO** cmdlets to aggregate multiple operations performed on a Group Policy Object (GPO).

You cannot use this parameter with the *PolicyStore* parameter.

```yaml
Type: String
Parameter Sets: ByGpoSession
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InputObject
Specifies the input object that is used in a pipeline command.

```yaml
Type: CimInstance[]
Parameter Sets: InputObject (cdxml)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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

### -PolicyStore
Specifies the policy store that contains the IP-HTTPS configuration profile to set.
The acceptable values for this parameter are:

- ActiveStore
- PersistentStore
- GPO

To set the configuration profile of a GPO, specify the GPO name using the following format: Domain\GPOName

You cannot use this parameter with the *GPOSession* parameter.

```yaml
Type: String
Parameter Sets: ByPolicyStore
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Profile
Specifies the name of the profile to modify.
This parameter is only allowed when the store is a GPO.

```yaml
Type: String[]
Parameter Sets: ByPolicyStore, ByGpoSession
Aliases: IPHttpsProfile

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ProfileActivated
Filters the objects to modify.

```yaml
Type: Boolean[]
Parameter Sets: ByPolicyStore, ByGpoSession
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ServerURL
Specifies the URL for the server.
If the profile is a client profile, Windows attempts to connect to the server URL.
If the profile is a server profile, then this is the URL to which the server listens.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -State
Specifies the state behavior of IP-HTTPS.
The acceptable values for this parameter are:

- Default.
 ---- For a server interface, IP-HTTPS is always configured.
---- For a client interface, IP-HTTPS is configured on demand based on the other connectivity options available.
Client interfaces are created with this setting by default.
- Enabled.
IP-HTTPS is always configured, for both server interfaces and client interfaces.
Server interfaces are created with this setting by default.
- Disabled.
Disables the IP-HTTPS interface.
- OutsideEnabled.
IP-HTTPs is configured on demand whenever the computer is outside of the corporate network.

```yaml
Type: State
Parameter Sets: (All)
Aliases:
Accepted values: Default, Enabled, Disabled, OutsideEnabled

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StrongCRLRequired
Determines if a strong certificate revocation list (CRL) check is required before connection.

The default value is False.

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
The parameter value set to server mode is only allowed on Windows Server 2012 or Windows Server 2016.

```yaml
Type: Type
Parameter Sets: (All)
Aliases:
Accepted values: Client, Server

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

### None
This cmdlet accepts no input objects.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root\StandardCimv2\MSFT_NetIpHTTPsConfiguration
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

When the *Passthru* parameter is specified, this cmdlet outputs a modified IP-HTTPS configuration object.

## NOTES

## RELATED LINKS

[Get-NetIPHttpsConfiguration](./Get-NetIPHttpsConfiguration.md)

[New-NetIPHttpsConfiguration](./New-NetIPHttpsConfiguration.md)

[Rename-NetIPHttpsConfiguration](./Rename-NetIPHttpsConfiguration.md)

[Remove-NetIPHttpsConfiguration](./Remove-NetIPHttpsConfiguration.md)

[Reset-NetIPHttpsConfiguration](./Reset-NetIPHttpsConfiguration.md)

