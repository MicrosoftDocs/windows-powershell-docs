---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: IpamDhcpConfigurationEvent.cdxml-help.xml
Module Name: IpamServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/ipamserver/remove-ipamdhcpconfigurationevent?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-IpamDhcpConfigurationEvent
---

# Remove-IpamDhcpConfigurationEvent

## SYNOPSIS
Removes configuration events for DHCP servers from the IPAM database.

## SYNTAX

```
Remove-IpamDhcpConfigurationEvent -EndDate <DateTime> [-PassThru] [-Force] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-IpamDhcpConfigurationEvent** cmdlet removes configuration events for Dynamic Host Configuration Protocol (DHCP) servers from the IP Address Management (IPAM) database.
The cmdlet permanently deletes configuration events through the specified end date.
The end date uses the time zone of the IPAM server.

Use the **Get-IpamDhcpConfigurationEvent** cmdlet to view configuration events from the IPAM database.

Do not specify the current date as the end date.
The IPAM server collects the configuration events from DHCP servers as part of the next data gathering task, and, therefore, specifies that the current date does not result in permanent deletion of events from the current day.

The cmdlet does not delete the configuration events from the DHCP servers themselves.

## EXAMPLES

### Example 1: Remove events through the previous day
```
PS C:\> $Today = Get-Date
PS C:\> Remove-IpamConfigurationEvent -EndDate $Today.AddDays(-1)
```

This example removes all configuration events through the previous day.

The first command creates a **DateTime** object by using the **Get-Date** cmdlet, and then stores it in the $Today variable.
By default, **Get-Date** creates the current date.
For more information about **Get-Date** and **DateTime** objects, type `Get-Help Get-Date`.

The second command removes configuration events from the IPAM database through the previous day.
The command subtracts one day from the **DateTime** object stored in the $Today variable, and then specifies that value for the *EndDate* parameter.

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

### -EndDate
Specifies the end date as a **DateTime** object.
The cmdlet removes events through this date from the IPAM database.
To obtain a **DateTime** object, use the **Get-Date** cmdlet.
For more information, type `Get-Help Get-Date`.

Do not specify the current date.

```yaml
Type: DateTime
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
Forces the command to run without asking for user confirmation.

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

## OUTPUTS

### IpamDhcpConfigurationEvent
This cmdlet returns an object that represents a DHCP server configuration event in IPAM.

## NOTES

## RELATED LINKS

[Get-IpamDhcpConfigurationEvent](./Get-IpamDhcpConfigurationEvent.md)

