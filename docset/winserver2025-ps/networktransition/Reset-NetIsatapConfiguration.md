---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_NetISATAPConfiguration.cdxml-help.xml
Module Name: NetworkTransition
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/networktransition/reset-netisatapconfiguration?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Reset-NetIsatapConfiguration
---

# Reset-NetIsatapConfiguration

## SYNOPSIS
Resets ISATAP configuration elements contained in a GPO.

## SYNTAX

### ByName (Default)
```
Reset-NetIsatapConfiguration [-IPInterface <CimInstance>] [-PolicyStore <String>] [-GPOSession <String>]
 [-State] [-Router] [-ResolutionState] [-ResolutionIntervalSeconds] [-PassThru] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject (cdxml)
```
Reset-NetIsatapConfiguration -InputObject <CimInstance[]> [-State] [-Router] [-ResolutionState]
 [-ResolutionIntervalSeconds] [-PassThru] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Reset-NetIsatapConfiguration** cmdlet resets ISATAP configuration elements contained in a Group Policy Object (GPO) to the not configured state.

Group Policy settings have one of the following three states: not configured, enabled, or disabled.

## EXAMPLES

### Example 1: Reset ISATAP configuration
```
PS C:\>Get-NetIPInterface -InterfaceIndex 14 | Reset-NetIsatapConfiguration -Router
```

This command retrieves an interface with an index 14 using the Get-NetIPInterface cmdlet, and then resets the router configuration for the ISATAP configuration of the specified interface using this cmdlet.

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
Specifies the Group Policy session that contains the ISATAP configuration to reset.

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
Specifies the IP interface on which to reset the ISATAP configurations.

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
Specifies the policy store that contains the ISATAP configuration to reset.
The acceptable values for this parameter are:

- ActiveStore

- PersistentStore

- GPO

To reset the configuration of a GPO, specify the GPO name using the following format: Domain\GPOName

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

### -ResolutionState
Resets the resolution state to not configured.

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

### -Router
Resets the router configuration to not configured.

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

### -State
Resets the state of the ISATAP configuration to not configured.

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

### Microsoft.Management.Infrastructure.CimInstance#root\StandardCimv2\MSFT_NetISATAPConfiguration
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

When the *Passthru* parameter is specified, this cmdlet outputs a modified Windows Management Instrumentation (WMI) object.

## NOTES

## RELATED LINKS

[Get-NetIsatapConfiguration](./Get-NetIsatapConfiguration.md)

[Set-NetIsatapConfiguration](./Set-NetIsatapConfiguration.md)

