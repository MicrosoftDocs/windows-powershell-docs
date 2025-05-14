---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_DAClientExperienceConfiguration.cdxml-help.xml
Module Name: DirectAccessClientComponents
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/directaccessclientcomponents/set-daclientexperienceconfiguration?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-DAClientExperienceConfiguration
---

# Set-DAClientExperienceConfiguration

## SYNOPSIS
Modifies the configuration of the specified DirectAccess client user experience.

## SYNTAX

### ByName (Default)
```
Set-DAClientExperienceConfiguration [-PolicyStore <String>] [-GPOSession <String>]
 [[-CorporateResources] <String[]>] [[-IPsecTunnelEndpoints] <String[]>] [[-PreferLocalNamesAllowed] <Boolean>]
 [[-UserInterface] <Boolean>] [[-SupportEmail] <String>] [[-FriendlyName] <String>]
 [[-ManualEntryPointSelectionAllowed] <Boolean>] [[-GslbFqdn] <String>] [[-ForceTunneling] <ForceTunneling>]
 [[-CustomCommands] <String[]>] [[-PassiveMode] <Boolean>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject (cdxml)
```
Set-DAClientExperienceConfiguration -InputObject <CimInstance[]> [[-CorporateResources] <String[]>]
 [[-IPsecTunnelEndpoints] <String[]>] [[-PreferLocalNamesAllowed] <Boolean>] [[-UserInterface] <Boolean>]
 [[-SupportEmail] <String>] [[-FriendlyName] <String>] [[-ManualEntryPointSelectionAllowed] <Boolean>]
 [[-GslbFqdn] <String>] [[-ForceTunneling] <ForceTunneling>] [[-CustomCommands] <String[]>]
 [[-PassiveMode] <Boolean>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-DAClientExperienceConfiguration** cmdlet modifies the specified configuration properties of the DirectAccess client user experience.
The DirectAccess client configuration controls the user interface behavior, as well as what configuration options are available to the user.

This cmdlet can be used to change configuration properties stored in Group Policy Objects.

## EXAMPLES

### Example 1: Disable the DirectAccess user interface
```
PS C:\>Set-DAClientExperienceConfiguration -PolicyStore "Contoso\GPO1" -UserInterface "False"
```

This cmdlet disables the DirectAccess user interface.

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
Configures the connectivity tests that DirectAccess client computers use to determine connectivity.
Enter the values for this parameter in the form of a string array, with each entry surrounded by double quotes (" ") and separated by commas.
Use the following formats for each test type:

HTTP test: `"HTTP:http://computername"`

File test: `"FILE:\\fileserver\"`

Ping test: `"PING:testURL"`

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CustomCommands
Configures any custom commands required by the administrator.
The custom commands are incorporated into the logs that are generated when there are problems.
Commands run in an elevated Windows PowerShell console sequentially.

Each item in the string array must be an individual command.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 10
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ForceTunneling
Configures the force tunneling setting on a DirectAccess client computer.
The acceptable values for this parameter are:

- Enabled
- Disabled
- Default

By default, force tunneling is disabled.

```yaml
Type: ForceTunneling
Parameter Sets: (All)
Aliases:
Accepted values: Default, Enabled, Disabled

Required: False
Position: 9
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FriendlyName
Specifies the name of the DirectAccess deployment to be shown in the client computer user interface.
It is recommended that the name be 15 characters or less.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 6
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
Specifies the fully-qualified domain name (FQDN) used for DirectAccess multisite client computers.
The client computer resolves the FQDN to an IP address, and compares the IP address to the list of entry points.
Client computers use the matching entry point for connectivity.

Specify the value for *GslbFqdn* in double quotes (" ").

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 8
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IPsecTunnelEndpoints
Configures the IPsec tunnel endpoints to use for DirectAccess.
Client computers use this information to verify the availability of the DirectAccess servers and present that information to the user.

Specify the values for *IPsecTunnelEndpoints* in double quotes (" "), separated by commas, in the format:

"Ping: ipaddress"

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Specifies the input to this cmdlet.
You can use this parameter, or you can pipe the input to this cmdlet.

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
Specifies if the user of a client computer can change the site used for DirectAccess connectivity.
If *ManualEntryPointSelectionAllowed* is set to $True, then users can change the entry point configuration in the user interface.
If *ManualEntryPointSelectionAllowed* is set to $False, then users cannot change the entry point configuration in the user interface.
By default, *ManualEntryPointSelectionAllowed* is set to $True.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: 7
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
Controls the passive mode setting on DirectAccess client computers.
In order to report DirectAccess status to the user, DirectAccess performs a set of tests frequently.
When *PassiveMode* is set to $True, those tests happen much less frequently.
However, enabling passive mode makes the client experience less responsive.

Valid values for *PassiveMode* are True or False.
By default, *PassiveMode* is set to False, which is the recommended setting.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: 11
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PolicyStore
Specifies the policy store into which the cmdlet stores the configuration information.

To store the configuration information in a Group Policy Object, specify the GPO name using the format "Domain\GPOName".

To store the configuration information in a computer's local GPO, specify the computer's local GPO name in the format "GPO:\<computername\>".

*PolicyStore* cannot be used in conjunction with *GPOSession*.

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
Indicates whether users can disconnect DirectAccess.
Disconnecting DirectAccess temporarily deactivates the name resolution policy table.

Valid values for *PreferLocalNamesAllowed* are True or False.
If set to True, users can disconnect DirectAccess.
The default value is False.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SupportEmail
Configures the email address displayed in the user interface for users to send logs and requests for assistance.
*SupportEmail* must be configured for logging to work.

Specify *SupportEmail* in the format of a valid email address.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 5
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
Enables or disables the user interface for DirectAccess on the client computers that receive the policy.

Valid values for *UserInterface* are True or False.
Setting *UserInterface* to False removes the user interface.
By default, *UserInterface* is set to True.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: 4
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

[Reset-DAClientExperienceConfiguration](./Reset-DAClientExperienceConfiguration.md)

