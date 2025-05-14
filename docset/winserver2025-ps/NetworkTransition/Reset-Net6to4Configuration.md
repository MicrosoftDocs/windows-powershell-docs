---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_Net6to4Configuration.cdxml-help.xml
Module Name: NetworkTransition
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/networktransition/reset-net6to4configuration?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Reset-Net6to4Configuration
---

# Reset-Net6to4Configuration

## SYNOPSIS
Resets the GPO settings for a 6to4 configuration.

## SYNTAX

### ByName (Default)
```
Reset-Net6to4Configuration [-IPInterface <CimInstance>] [-PolicyStore <String>] [-GPOSession <String>] [-State]
 [-AutoSharing] [-RelayName] [-RelayState] [-ResolutionIntervalSeconds] [-PassThru]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject (cdxml)
```
Reset-Net6to4Configuration -InputObject <CimInstance[]> [-State] [-AutoSharing] [-RelayName] [-RelayState]
 [-ResolutionIntervalSeconds] [-PassThru] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Reset-Net6to4Configuration** cmdlet resets the Group Policy Object (GPO) settings for a 6to4 configuration to the not configured state.
Group Policy settings have three possible states: not configured, enabled, and disabled.

6to4 is an address assignment and router-to-router automatic tunneling technology that is described in [RFC 3056: Connection of IPv6 Domains via IPv4 Clouds](https://go.microsoft.com/fwlink/p/?LinkId=256388).
6to4 provides a globally-routable IPv6 address to a host with a public IPv4 address.
This IPv6 address can be used to connect to other 6to4 hosts or the IPv6 Internet.

## EXAMPLES

### Example 1: Reset the 6to4 configuration of an interface
```
PS C:\>$config = ( Get-NetIPInterface -InterfaceIndex 14 | Get-Net6to4Configuration )
PS C:\> Reset-Net6to4Configuration -InputObject $config
```

This set of commands uses the Get-NetIPInterface cmdlet to get the configuration information for the interface at index 14 and then passes the interface configuration to the Get-Net6to4Configuration cmdlet to get the 6to4 configuration.
The result is stored in a variable named $config.
The contents of the variable are then passed to this cmdlet.

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
Resets the AutoSharing policy element to not configured.
You can configure this parameter by using the Set-Net6to4Configuration cmdlet.

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
Specifies the Group Policy session in which to store the configuration information.

You can use this parameter with the **NetGPO** cmdlets to aggregate multiple operations performed on a GPO.

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
Specifies the IP interface on which to reset the 6to4 configuration.

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
Specifies the policy store that contains the 6to4 configuration to reset.
For this cmdlet, this parameter only supports GPO stores.

To reset a 6to4 configuration stored in a GPO, specify the GPO name using the following format: Domain\GPOName

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
Resets the 6to4 relay name to not configured.

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

### -RelayState
Resets the 6to4 relay state to not configured.

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

### -ResolutionIntervalSeconds
Resets the resolution interval to not configured.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: ResolutionInterval

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -State
Resets the state of the 6to4 configuration to not configured.

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

## NOTES
* When the *Passthru* parameter is specified, this cmdlet outputs a modified Windows Management Instrumentation (WMI) object.

## RELATED LINKS

[Get-Net6to4Configuration](./Get-Net6to4Configuration.md)

[Set-Net6to4Configuration](./Set-Net6to4Configuration.md)

