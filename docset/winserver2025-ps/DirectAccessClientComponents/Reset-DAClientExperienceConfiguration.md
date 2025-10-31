---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_DAClientExperienceConfiguration.cdxml-help.xml
Module Name: DirectAccessClientComponents
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/directaccessclientcomponents/reset-daclientexperienceconfiguration?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Reset-DAClientExperienceConfiguration
---

# Reset-DAClientExperienceConfiguration

## SYNOPSIS
Restores the specified DirectAccess client configuration to the defaults.

## SYNTAX

### ByName (Default)
```
Reset-DAClientExperienceConfiguration [-PolicyStore <String>] [-GPOSession <String>] [-CorporateResources]
 [-IPsecTunnelEndpoints] [-PreferLocalNamesAllowed] [-UserInterface] [-SupportEmail] [-FriendlyName]
 [-ManualEntryPointSelectionAllowed] [-GslbFqdn] [-ForceTunneling] [-CustomCommands] [-PassiveMode] [-PassThru]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject (cdxml)
```
Reset-DAClientExperienceConfiguration -InputObject <CimInstance[]> [-CorporateResources]
 [-IPsecTunnelEndpoints] [-PreferLocalNamesAllowed] [-UserInterface] [-SupportEmail] [-FriendlyName]
 [-ManualEntryPointSelectionAllowed] [-GslbFqdn] [-ForceTunneling] [-CustomCommands] [-PassiveMode] [-PassThru]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Reset-DAClientExperienceConfiguration** cmdlet restores the specified DirectAccess client configuration to the defaults.

All **DAClientExperienceConfiguration** cmdlets have an ADMX file which can also configure these settings.

## EXAMPLES

### Example 1: Reset the friendly name of a client experience configuration
```
PS C:\>Reset-DAClientExperienceConfiguration -PolicyStore "Contoso\GPO1" -FriendlyName "Traveling Policy"
```

This cmdlet resets the friendly name of a client experience configuration.

## PARAMETERS

### -AsJob
Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to complete.

The cmdlet immediately returns an object that represents the job and then displays the command prompt.
You can continue to work in the session while the job completes.
To manage the job, use the `*-Job` cmdlets.
To get the job results, use the [Receive-Job](https://go.microsoft.com/fwlink/?LinkID=113372) cmdlet.

For more information about Windows PowerShell background jobs, see [about_Jobs](https://go.microsoft.com/fwlink/?LinkID=113251).

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

### -CorporateResources
Resets the CorporateResources property of the specified configuration to a non-configured state.

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

### -CustomCommands
Resets the CustomCommands property of the specified configuration to a non-configured state.

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

### -ForceTunneling
Resets the ForceTunneling property of the specified configuration to a non-configured state.

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

### -FriendlyName
Resets the FriendlyName property of the specified configuration to a non-configured state.

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

### -GPOSession
Specifies the Group Policy session to send configuration information.
You can use *GPOSession* with the **NetGPO** cmdlets to aggregate multiple operations performed on a Group Policy Object.

*GPOSession* cannot be used in conjunction with *PolicyStore*.

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

### -GslbFqdn
Resets the GslbFqdn property of the specified configuration to a non-configured state.

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

### -IPsecTunnelEndpoints
Resets the IPsecTunnelEndpoints property of the specified configuration to a non-configured state.

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

### -ManualEntryPointSelectionAllowed
Resets the ManualEntryPointSelectionAllowed property of the specified configuration to a non-configured state.

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

### -PassThru
Sends items from an interactive window down the pipeline as input to other cmdlets.
By default, this cmdlet does not generate any output.
However, to send items from the interactive window down the pipeline, click to select the items and then click OK.
Shift-click and Ctrl-click are supported.

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

### -PassiveMode
Resets the PassiveMode property of the specified configuration to a non-configured state.

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
Specifies the policy store into which the cmdlet adds the reset configuration properties.

To add the reset configuration properties to a Group Policy Object, specify the GPO name using the format "Domain\GPOName".

To add the reset configuration properties to a computer's local GPO, specify the computer's local GPO name in the format "GPO:\<computername\>".

**PolicyStore** cannot be used in conjunction with **GPOSession**.

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

### -PreferLocalNamesAllowed
Resets the PreferLocalNamesAllowed property of the specified configuration to a non-configured state.

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

### -SupportEmail
Resets the SupportEmail property of the specified configuration to a non-configured state.

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

### -UserInterface
Resets the UserInterface property of the specified configuration to a non-configured state.

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

### Microsoft.Management.Infrastructure.CimInstance#root/StandardCimv2/MSFT_DAClientExperienceConfiguration
This cmdlet accepts as input a CIM object that contains a DA client experience configuration.

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Get-DAClientExperienceConfiguration](./Get-DAClientExperienceConfiguration.md)

[Set-DAClientExperienceConfiguration](./Set-DAClientExperienceConfiguration.md)

