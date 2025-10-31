---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_DASiteTableEntry.cdxml-help.xml
Module Name: DirectAccessClientComponents
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/directaccessclientcomponents/new-daentrypointtableitem?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-DAEntryPointTableItem
---

# New-DAEntryPointTableItem

## SYNOPSIS
Configures a new entry point for multisite DirectAccess.

## SYNTAX

### ByPolicyStore (Default)
```
New-DAEntryPointTableItem [-PolicyStore] <String> -EntryPointName <String> -ADSite <String>
 -EntryPointRange <String[]> [-TeredoServerIP <String>] -EntryPointIPAddress <String> [-GslbIP <String>]
 [-IPHttpsProfile <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ByGpoSession
```
New-DAEntryPointTableItem -EntryPointName <String> -ADSite <String> -EntryPointRange <String[]>
 [-TeredoServerIP <String>] -EntryPointIPAddress <String> [-GslbIP <String>] [-IPHttpsProfile <String>]
 [-GPOSession] <String> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **New-DAEntryPointTableItem** cmdlet configures a new entry point for multisite DirectAccess.
The administrator distributes the new entry point to DirectAccess client computers by using Group Policy, and DirectAccess client computers use the new entry point when appropriate.

## EXAMPLES

### Example1: Create a new entry point
```
PS C:\> New-DAEntryPointTableItem -PolicyStore "GPO:Localhost" -ADSite "Paris" -EntryPointRange "2001::/16" -TeredoServerIP "131.107.1.1" -EntryPointIPAddress "200::1" -GslbIP "131.107.0.1" -EntryPointName "Paris"
```

This cmdlet creates a simple entry point named Paris.

## PARAMETERS

### -ADSite
Specifies the Active Directory Domain Services (AD DS) site name associated with the entry point.
When a client computer connects to an entry point, the computer becomes associated with the AD DS site specified.

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

### -EntryPointIPAddress
Specifies the IPv6 address of the entry point to use for connectivity.
The cmdlet fails if the IP address specified is not within the IP address range specified by *EntryPointRange*.

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

### -EntryPointName
Specifies the name of the entry point.
The entry point name is usually the friendly name of the location, such as Redmond or Paris.

Specify the name of the entry point by using double quotes (" ").

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

### -EntryPointRange
Specifies the IPv6 address range associated with computers connecting through this entry point.
Specify the IPv6 range in classless inter-domain routing (CIDR) notation.

The following is an example of an *EntryPointRange* entry:

`{2001:4898:e0:305d::100:1/128, 2001:4898:e0:305d::100:2/128, 2001:4898:e0:3084::/64}`

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: True
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
Parameter Sets: ByGpoSession
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GslbIP
Specifies the IP address associated with the new entry point, if using DirectAccess in conjunction with global server load balancing (GSLB) site balancing.

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

### -IPHttpsProfile
Specifies the IPHTTPs profile name to be used for connectivity.
You specify the name of the profile in double quotes (" ").
**New-DAEntryPointTableItem** fails if the profile does not already exist in the GPO that contains the configuration.
For more information about IPHTTPs profiles, see the **NetIPHTTPsConfiguration** cmdlets in the **NetworkTransition** module.

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

### -PolicyStore
Specifies the policy store into which the cmdlet adds the entry point.

To add the entry point to a Group Policy Object, specify the GPO name using the following format: "Domain\GPOName"

To add the entry point information to a computer's local GPO, specify the computer's local GPO name in the following format: "GPO:\<computername\>"

*PolicyStore* cannot be used in conjunction with *GPOSession*.

```yaml
Type: String
Parameter Sets: ByPolicyStore
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TeredoServerIP
Specifies the IP address of the Teredo server for the new entry point.

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

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/StandardCimv2/MSFT_DASiteTableEntry
This cmdlet returns a CIM object which contains the new DA entry point table item.

## NOTES

## RELATED LINKS

[Get-DAEntryPointTableItem](./Get-DAEntryPointTableItem.md)

[Remove-DAEntryPointTableItem](./Remove-DAEntryPointTableItem.md)

[Rename-DAEntryPointTableItem](./Rename-DAEntryPointTableItem.md)

[Reset-DAEntryPointTableItem](./Reset-DAEntryPointTableItem.md)

[Set-DAEntryPointTableItem](./Set-DAEntryPointTableItem.md)

