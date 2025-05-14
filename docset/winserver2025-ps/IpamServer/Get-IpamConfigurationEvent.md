---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: IpamConfigurationEvent.cdxml-help.xml
Module Name: IpamServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/ipamserver/get-ipamconfigurationevent?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-IpamConfigurationEvent
---

# Get-IpamConfigurationEvent

## SYNOPSIS
Gets IPAM configuration events from the IPAM database.

## SYNTAX

```
Get-IpamConfigurationEvent [-UserName <String[]>] [-UserDomainName <String[]>] [-UserForestName <String[]>]
 [-StartDate <DateTime>] [-EndDate <DateTime>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-IpamConfigurationEvent** cmdlet gets IP Address Management (IPAM) configuration events from the IPAM database.
If you do not specify any parameters, the cmdlet gets all configuration events for the IPAM server.
You can specify the *StartDate* and *EndDate* parameters to get configuration events that occur in a span of time.
You can specify the *UserDomainName* parameter to filter configuration events that occur in a user domain.
You can specify the *UserName* parameter to filter configuration changes made by a user.

Specify values for the *StartDate* and *EndDate* parameters in the time zone of the IPAM server.
The cmdlet returns data that includes both the start date and end date.
If you do not specify the *StartDate* parameter, the cmdlet uses the start date of the first IPAM configuration event in the IPAM database.
If you do not specify the *EndDate* parameter, the cmdlet uses the date of the last available server configuration event in IPAM.

If there are more than 10,000 results for a command, the cmdlet returns only the first 10,000.
The cmdlet warns that this is a partial result.

## EXAMPLES

### Example 1: Get IPAM server configuration events for a span of time
```
PS C:\> $Today = Get-Date
PS C:\> $LastMonth = $Today.AddDays(-30)
PS C:\> Get-IpamConfigurationEvent -StartDate $LastMonth -EndDate $Today
```

This example gets all configuration events for the IPAM server in last 30 days.

The first command creates a **DateTime** object by using the **Get-Date** cmdlet, and then stores it in the $Today variable.
By default, **Get-Date** creates the current date.
For more information about **Get-Date** and **DateTime** objects, type `Get-Help Get-Date`.

The second command subtracts 30 days from the **DateTime** object stored in the $Today variable, and then stores the result in the $LastMonth variable.

The third command gets the configuration events for the IPAM server in the last 30 days.

### Example 2: Get IPAM configuration events for a user
```
PS C:\> $Today = Get-Date
PS C:\> $LastMonth = $Today.AddDays(-30)
PS C:\> Get-IpamConfigurationEvent -StartDate $LastMonth -EndDate $Today -UserName "Administrator"
```

This example gets all configuration events for the IPAM server in last 30 days for a user.

The first command creates a **DateTime** object by using the **Get-Date** cmdlet, and then stores it in the $Today variable.
By default, **Get-Date** creates the current date.

The second command subtracts 30 days from the **DateTime** object stored in the $Today variable, and then stores the result in the $LastMonth variable.

The third command gets the configuration events for the IPAM server in the last 30 days for the user named Administrator.

### Example 3: Get IPAM configuration events for User from domain
```
PS C:\> $Today = Get-Date
PS C:\> $LastMonth = $Today.AddDays(-30)
PS C:\> Get-IpamConfigurationEvent -StartDate $LastMonth -EndDate $Today -UserName "Administrator" -UserDomainName "Contoso.com"
```

This example gets all the configuration events for the IPAM server in last 30 days for a user from a specified the domain.

The first command creates a **DateTime** object by using the **Get-Date** cmdlet, and then stores it in the $Today variable.
By default, **Get-Date** creates the current date.

The second command subtracts 30 days from the **DateTime** object stored in the $Today variable, and then stores the result in the $LastMonth variable.

The third command gets all the configuration events for the IPAM server in last 30 days for the user named Administrator from the domain named Contoso.com.

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
The cmdlet gets configuration events through this date from the IPAM database.
The cmdlet gets events from the start date through this date from the IPAM database.
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

### -StartDate
Specifies a start date as a **DateTime** object.
The cmdlet gets configuration events from this date through the end date from the IPAM database.
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

### -UserDomainName
Specifies an array of names of user domains.
The cmdlet filters configuration events that occur in this user domain.

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

### -UserForestName


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

### -UserName
Specifies an array of names of user names.
The cmdlet gets configuration events made by these users.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### IpamConfigurationEvent
This cmdlet returns an object that represents a configuration event for the IPAM server.

## NOTES

## RELATED LINKS

[Remove-IpamConfigurationEvent](./Remove-IpamConfigurationEvent.md)

