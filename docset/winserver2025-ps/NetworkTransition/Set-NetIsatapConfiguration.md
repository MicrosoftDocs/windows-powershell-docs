---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_NetISATAPConfiguration.cdxml-help.xml
Module Name: NetworkTransition
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/networktransition/set-netisatapconfiguration?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-NetIsatapConfiguration
---

# Set-NetIsatapConfiguration

## SYNOPSIS
Sets an ISATAP configuration on a computer or on a Group Policy Object (GPO).

## SYNTAX

### ByName (Default)
```
Set-NetIsatapConfiguration [-IPInterface <CimInstance>] [-PolicyStore <String>] [-GPOSession <String>]
 [[-State] <State>] [[-Router] <String>] [[-ResolutionState] <State>] [[-ResolutionIntervalSeconds] <UInt32>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### InputObject (cdxml)
```
Set-NetIsatapConfiguration -InputObject <CimInstance[]> [[-State] <State>] [[-Router] <String>]
 [[-ResolutionState] <State>] [[-ResolutionIntervalSeconds] <UInt32>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-NetIsatapConfiguration** cmdlet sets an ISATAP configuration on a computer or on a Group Policy Object (GPO).

## EXAMPLES

### Example 1: Set ISATAP configuration
```
PS C:\>Set-NetIsatapConfiguration -Router superisatap
```

This command modifies the router name.

### Example 2: Set a router using an input object
```
PS C:\>$config = ( Get-NetIPInterface -InterfaceIndex 14 | Get-NetIPISATAPConfiguration )
PS C:\> $config.Router = "SuperIsatap"
PS C:\> Set-NetIsatapConfiguration -InputObject $config
```

This set of commands uses the Get-NetIPInterface and Get-NetIsatapConfiguration cmdlets to get the ISATAP configuration of the interface at index 14 and stores it in a variable named $config, and then sets the router name to SuperIsatap using this cmdlet.

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

You can use this with the **NetGPO** cmdlets to aggregate multiple operations performed on a GPO.

You cannot use this parameter with the *PolicyStore* parameter.

```yaml
Type: String
Parameter Sets: ByName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IPInterface
Specifies the IP interface on which to set the ISATAP configuration.

```yaml
Type: CimInstance
Parameter Sets: ByName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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
Specifies the policy store that contains the configuration to set.
The acceptable values for this parameter are:

- PersistentStore
- ActiveStore
- GPO

To set the configuration of a GPO, specify the GPO name using the following format: Domain\GPOName

You cannot use this parameter with the *GPOSession* parameter.

```yaml
Type: String
Parameter Sets: ByName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResolutionIntervalSeconds
Specifies how often in seconds that Windows Server® 2012 attempts to contact the specified ISATAP server.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: ResolutionInterval

Required: False
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResolutionState
Specifies the state of router name resolution.
The state of the router name resolution specifies how often Windows Server 2012 resolves the ISATAP router name.

```yaml
Type: State
Parameter Sets: (All)
Aliases:
Accepted values: Default, Automatic, Enabled, Disabled

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Router
Specifies the policy setting that allows you to specify a router name or IPv4 address for an ISATAP router.

If you enable this policy setting, then you can specify a router name or IPv4 address for an ISATAP router.
If you enter an IPv4 address of the ISATAP router, then DNS services are not required.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -State
Specifies the policy setting that allows you to configure ISATAP, an address-to-router and host-to-host, host-to-router and router-to-host automatic tunneling technology that provides unicast IPv6 connectivity between IPv6 hosts across an IPv4 intranet.
You can specify one of the following three policy setting states:

- Default.
If the ISATAP router name is resolved successfully, then ISATAP is configured with a link-local address and an address for each prefix received from the ISATAP router through stateless address auto-configuration.

 ---- If the ISATAP router name is not resolved successfully, then ISATAP connectivity is not available on the host using the corresponding IPv4 address.

 -- Enabled.

 ---- If the ISATAP name is resolved successfully, then ISATAP is configured with a link-local address and an address for each prefix received from the ISATAP router through stateless address auto-configuration.

 ---- If the ISATAP name is not resolved successfully, then the ISATAP interface is configured with a link-local address.

 -- Disabled.
No ISATAP interfaces are present on the host.

```yaml
Type: State
Parameter Sets: (All)
Aliases:
Accepted values: Default, Automatic, Enabled, Disabled

Required: False
Position: 1
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

### None
This cmdlet accepts no input objects.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root\StandardCimv2\MSFT_NetISATAPConfiguration
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

When the *Passthru* parameter is specified, this cmdlet outputs a modified ISATAP configuration object.

## NOTES

## RELATED LINKS

[Get-NetIsatapConfiguration](./Get-NetIsatapConfiguration.md)

[Set-NetIsatapConfiguration](./Set-NetIsatapConfiguration.md)

