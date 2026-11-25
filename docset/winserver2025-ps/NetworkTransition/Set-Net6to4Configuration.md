---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_Net6to4Configuration.cdxml-help.xml
Module Name: NetworkTransition
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/networktransition/set-net6to4configuration?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Net6to4Configuration
---

# Set-Net6to4Configuration

## SYNOPSIS
Sets the 6to4 configuration for both client computers and servers.

## SYNTAX

### ByName (Default)
```
Set-Net6to4Configuration [-IPInterface <CimInstance>] [-PolicyStore <String>] [-GPOSession <String>]
 [[-State] <State>] [[-AutoSharing] <State>] [[-RelayName] <String>] [[-RelayState] <State>]
 [[-ResolutionIntervalSeconds] <UInt32>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject (cdxml)
```
Set-Net6to4Configuration -InputObject <CimInstance[]> [[-State] <State>] [[-AutoSharing] <State>]
 [[-RelayName] <String>] [[-RelayState] <State>] [[-ResolutionIntervalSeconds] <UInt32>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-Net6to4Configuration** cmdlet sets the 6to4 configuration of both client computers and servers.

6to4 is an address assignment and router-to-router automatic tunneling technology that is described in [RFC 3056: Connection of IPv6 Domains via IPv4 Clouds](https://go.microsoft.com/fwlink/p/?LinkId=256388).
6to4 provides a globally-routable IPv6 address to a host with a public IPv4 address.
This IPv6 address can be used to connect to other 6to4 hosts or the IPv6 Internet.

This cmdlet is similar in functionality to the `netsh interface 6to4 context` command.

## EXAMPLES

### Example 1: Modify the relay name on the persistent store
```
PS C:\>Set-Net6to4Configuration -RelayName "my6to4relay.com"
```

This command sets the relay name to my6to4relay.com for 6to4 connectivity on the local persistent store.

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

### -AutoSharing
Determines if 6to4 prefixes are forwarded when Internet Connection Sharing (ICS) is enabled.
By default, 6to4 prefixes are forwarded.

```yaml
Type: State
Parameter Sets: (All)
Aliases:
Accepted values: Default, Automatic, Enabled, Disabled

Required: False
Position: 2
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
Specifies the Group Policy session in which to store the 6to4 configuration information.

You can use this parameter with the **NetGPO** cmdlets to aggregate multiple operations performed on a Group Policy Object (GPO).

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
Specifies the IP interface on which to set the 6to4 configuration.

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

To set the configuration of a GPO, specify the GPO name using the following format: `Domain\GPOName`

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

### -RelayName
Specifies a 6to4 relay name.
If 6to4 connectivity is not available on the computer, the relay name setting has no effect.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RelayState
Configures the 6to4 relay state.
The acceptable values for this parameter are:

- Default.
If the host has link-local only IPv6 connectivity and a public IPv4 address, then 6to4 is enabled.
If there is no global IPv6 address present and no global IPv4 address present, then the host does not have a 6to4 interface.
If there is no global IPv6 address present but there is a global IPv4 address present, then the host has a 6to4 interface.
- Enabled.
If there is a global IPv4 address present, then the host has a 6to4 interface.
If there is no global IPv4 address present, then the host does not have a 6to4 interface.
- Disabled.
6to4 is turned off and connectivity with 6to4 is not available.
- Automatic.

```yaml
Type: State
Parameter Sets: (All)
Aliases:
Accepted values: Default, Automatic, Enabled, Disabled

Required: False
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResolutionIntervalSeconds
Specifies the frequency for resolving the relay name.
The 6to4 relay name resolution interval setting has no effect if there is no 6to4 connectivity available on the host.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: ResolutionInterval

Required: False
Position: 5
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -State
Specifies the state behavior of 6to4.
The acceptable values for this parameter are:

- Default.
If the host has link-local only IPv6 connectivity and a public IPv4 address, then 6to4 is enabled.
If there is no global IPv6 address present and no global IPv4 address present, then the host does not have a 6to4 interface.
If there is no global IPv6 address present but there is a global IPv4 address present, then the host has a 6to4 interface.
- Enabled.
If there is a global IPv4 address present, then the host has a 6to4 interface.
If there is no global IPv4 address present, then the host does not have a 6to4 interface.
- Disabled.
6to4 is turned off and connectivity with 6to4 is not available.
- Automatic.

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

### Microsoft.Management.Infrastructure.CimInstance#root\StandardCimv2\MSFT_Net6to4Configuration
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

When the *Passthru* parameter is specified, this cmdlet outputs a modified 6to4 configuration object.

## NOTES

## RELATED LINKS

[Get-Net6to4Configuration](./Get-Net6to4Configuration.md)

[Reset-Net6to4Configuration](./Reset-Net6to4Configuration.md)

