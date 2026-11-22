---
description: Sets the name of the network adapter, profile, and the profile source.
external help file: MSFT_NetAdapterDataPathConfiguration.cdxml-help.xml
Module Name: NetAdapter
ms.date: 09/22/2021
online version: https://learn.microsoft.com/powershell/module/netadapter/set-netadapterdatapathconfiguration?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-NetAdapterDataPathConfiguration
---

# Set-NetAdapterDataPathConfiguration

## SYNOPSIS
Sets the name of the network adapter, profile, and the profile source.

## SYNTAX

### ByName (Default)
```
Set-NetAdapterDataPathConfiguration [-Name] <String[]> [-IncludeHidden] [-Profile <String>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ByInstanceID
```
Set-NetAdapterDataPathConfiguration -InterfaceDescription <String[]> [-IncludeHidden] [-Profile <String>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### InputObject (cdxml)
```
Set-NetAdapterDataPathConfiguration -InputObject <CimInstance[]> [-Profile <String>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-NetAdapterDataPathConfiguration** cmdlet sets the name of the network adapter, profile,
and the profile source. The profile describes the datapath behavior of NDIS Poll Mode. NDIS Poll
Mode is an operating system controlled polling execution model that drives the network interface
datapath. Currently, Windows supports four built-in profiles for server and two built-in profiles
for client. The built-in profiles can only be set using PowerShell.

## EXAMPLES

### Example 1: Set the profile of a network adapter
```powershell
PS> Set-NetAdapterDataPathConfiguration -Name "Ethernet" -Profile Legacy
```

Sets the profile to **Legacy** for the network adapter named **Ethernet**.

## PARAMETERS

### -AsJob
Runs the cmdlet as a background job.
Use this parameter to run commands that take a long time to complete.
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

### -IncludeHidden
Indicates that this cmdlet includes both visible and hidden network adapters. By
default only visible network adapters are included. If a wildcard character is
used in identifying a network adapter and this parameter has been specified,
then the wildcard string is matched against both hidden and visible network
adapters.

```yaml
Type: SwitchParameter
Parameter Sets: ByName, ByInstanceID
Aliases:

Required: False
Position: Named
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

### -InterfaceDescription
Specifies an array of network adapter interface descriptions. For a physical
network adapter this is typically the name of the vendor of the network adapter
followed by a part number and description, such as
`Contoso 12345 Gigabit Network Device`.

```yaml
Type: String[]
Parameter Sets: ByInstanceID
Aliases: ifDesc, InstanceID

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies an array of network adapter names.

```yaml
Type: String[]
Parameter Sets: ByName
Aliases: ifAlias, InterfaceAlias

Required: True
Position: 0
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

### -Profile

Name of one of the four built-in profiles for the operating system.

The profile describes the datapath behavior of NDIS Poll Mode. NDIS Poll Mode is an operating system
controlled polling execution model that drives the network interface datapath.

Allowed values for this parameter are:
- Windows Server - **Dispatch** (default), **Balanced**, **Legacy mode**, and **Passive**.
- Windows client - **Balanced** (default)

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

### -ThrottleLimit
Specifies the maximum number of concurrent operations that can be established to
run the cmdlet. If this parameter is omitted or a value of `0` is entered, then
Windows PowerShell calculates an optimum throttle limit for the cmdlet based on
the number of CIM cmdlets that are running on the computer. The throttle limit
applies only to the current cmdlet, not to the session or to the computer.

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
Aliases: cf

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
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String[]
### Microsoft.Management.Infrastructure.CimInstance[]
## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance

## NOTES

## RELATED LINKS
