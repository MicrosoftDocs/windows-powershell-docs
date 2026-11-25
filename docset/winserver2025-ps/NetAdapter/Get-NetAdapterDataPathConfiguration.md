---
description: Gets the name of the network adapter, profile, and the profile source.
external help file: MSFT_NetAdapterDataPathConfiguration.cdxml-help.xml
Module Name: NetAdapter
ms.date: 09/23/2021
online version: https://learn.microsoft.com/powershell/module/netadapter/get-netadapterdatapathconfiguration?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-NetAdapterDataPathConfiguration
---

# Get-NetAdapterDataPathConfiguration

## SYNOPSIS
Gets the name of the network adapter, profile, and the profile source.

## SYNTAX

### ByName (Default)
```
Get-NetAdapterDataPathConfiguration [[-Name] <String[]>] [-Profile <String[]>] [-ProfileSource <UInt32[]>]
 [-IncludeHidden] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByInstanceID
```
Get-NetAdapterDataPathConfiguration -InterfaceDescription <String[]> [-Profile <String[]>]
 [-ProfileSource <UInt32[]>] [-IncludeHidden] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-NetAdapterDataPathConfiguration** cmdlet gets the name of the network adapter, profile,
and the profile source. The profile describes the datapath behavior of NDIS Poll Mode. NDIS Poll
Mode is an operating system controlled polling execution model that drives the network interface
datapath.

## EXAMPLES

### Example 1: Get datapath information for network adapter
```powershell
PS> Get-NetAdapterDataPathConfiguration -Name "Ethernet"
```

Gets the datapath profile and profile source information for the network adapter named **Ethernet**.

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
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Profile
Name of one of the four built-in profiles for the operating system.

The profile describes the datapath behavior of NDIS Poll Mode. NDIS Poll Mode is an operating system
controlled polling execution model that drives the network interface datapath.

Allowed values for this parameter are: **Legacy mode**, **Balanced**, **Passive**, and **Dispatch**.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ProfileSource

Indicates the source of the profile configuration source. Values include **BuiltIn** and
**Custom**.

```yaml
Type: UInt32[]
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String[]
## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance

## NOTES

## RELATED LINKS
