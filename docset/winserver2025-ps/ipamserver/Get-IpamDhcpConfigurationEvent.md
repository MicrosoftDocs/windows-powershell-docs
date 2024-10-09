---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: IpamDhcpConfigurationEvent.cdxml-help.xml
Module Name: IpamServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/ipamserver/get-ipamdhcpconfigurationevent?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-IpamDhcpConfigurationEvent
---

# Get-IpamDhcpConfigurationEvent

## SYNOPSIS
Gets configuration events for DHCP servers from the IPAM database.

## SYNTAX

```
Get-IpamDhcpConfigurationEvent [-ServerName <String[]>] [-StartDate <DateTime>] [-EndDate <DateTime>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-IpamDhcpConfigurationEvent** cmdlet gets configuration events for Dynamic Host Configuration Protocol (DHCP) servers from the IP Address Management (IPAM) database.
You can specify fully qualified domain names (FQDNs) of DHCP servers, a start date, and an end date.
If you do not specify a DHCP server, the cmdlet gets configuration events for all servers.

Use the **Remove-IpamDhcpConfigurationEvent** cmdlet to remove events from the database.

If you do not specify a start date, the cmdlet uses the date of the first IPAM configuration event in the database.
If you do not specify an end date, the cmdlet uses the date of the last IPAM configuration event.
All dates use the time zone of the IPAM server.

If there are more than 10,000 results for a command, the cmdlet returns only 10,000.
The cmdlet warns that this is a partial result.

## EXAMPLES

### Example 1: Get events for all servers for a date range
```
PS C:\> $Today = Get-Date
PS C:\> $StartDate= $Today.AddDays(-7)
PS C:\> Get-IpamDhcpConfigurationEvent -EndDate $Today -StartDate $StartDate | Export-Csv "C:\IpamEvents.csv"
```

This example gets the configuration events for all DHCP servers, and then saves them as a .csv file.

The first command creates a **DateTime** object by using the **Get-Date** cmdlet, and then stores it in the $Today variable.
By default, **Get-Date** creates the current date.
For more information about **Get-Date** and **DateTime** objects, type `Get-Help Get-Date`.

The second command stores a new **DateTime** object in the $StartTime variable.
That date is seven days prior to the date stored in the $Today variable.

The third command gets configuration events between the start date, stored in the $StartTime variable, and the end date, stored in the $Today variable, for all DHCP servers.
The command passes the events to the **Export-Csv** cmdlet through the pipeline operator.
That cmdlet saves the results as a .csv file.
For more information about this cmdlet, type `Get-Help Export-Csv`.

### Example 2: Get events for specified servers for a date range
```
PS C:\> $Today = Get-Date
PS C:\> $StartDate= $Today.AddDays(-7)
PS C:\> Get-IpamConfigurationEvent -EndDate $Today -ServerName "dhcp01.contoso.com","dhcp02.contoso.com" -StartDate $StartDate | Export-Csv "C:\IpamFilteredEvents.csv"
```

This example gets the configuration events for two DHCP servers, and then saves them as a .csv file.

The first command creates a **DateTime** object by using the **Get-Date** cmdlet, and then stores it in the $Today variable.

The second command stores a new **DateTime** object in the $StartTime variable.
That date is seven days prior to the date stored in the $Today variable.

The third command gets configuration events between the start date, stored in the $StartDate variable, and the end date, stored in the $Today variable.
The command specifies the FQDNs of two DHCP servers.
The command passes the events to the **Export-Csv** cmdlet through the pipeline operator.
That cmdlet saves the results as a .csv file.

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

### -EndDate
Specifies the end date as a **DateTime** object.
The cmdlet gets events through this date from the IPAM database.
To obtain a **DateTime** object, use the **Get-Date** cmdlet and specify the date in **DD/MM/YYYY** format.
For more information, type `Get-Help Get-Date`.

```yaml
Type: DateTime
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServerName
Specifies an array of FQDNs of DHCP servers.

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

### -StartDate
Specifies the start date as a **DateTime** object.
The cmdlet gets events beginning with this date.
To obtain a **DateTime** object, use the **Get-Date** cmdlet and specify the date in **DD/MM/YYYY** format.

```yaml
Type: DateTime
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### IpamDhcpConfigurationEvent
This cmdlet returns an object that represents a DHCP server configuration event in IPAM.

## NOTES

## RELATED LINKS

[Remove-IpamDhcpConfigurationEvent](./Remove-IpamDhcpConfigurationEvent.md)

