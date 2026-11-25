---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: ServerManagerTasks.cdxml-help.xml
Module Name: ServerManagerTasks
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/servermanagertasks/get-smserverevent?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-SMServerEvent
---

# Get-SMServerEvent

## SYNOPSIS
Gets the details of events generated in a Server Manager event log.

## SYNTAX

```
Get-SMServerEvent [-Log <String[]>] [-Level <EventLevelFlag[]>] [-StartTime <UInt64[]>] [-EndTime <UInt64[]>]
 [-BatchSize <UInt32>] [-QueryFile <String[]>] [-QueryFileId <Int32[]>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SMServerEvent** cmdlet gets the details of events from a server that is running Windows Server, in one of the five Server Manager event log channels.

## EXAMPLES

### Example 1: Get Server Manager Management Provider events
```
PS C:\>Get-SMServerEvent -Log 'Microsoft-Windows-ServerManager-MgmtProvider/Operational' | Format-Table -Property Description,Source
```

This command gets the events in the Server Manager Management Provider Operational event log channel.
Because no batch size is specified, the command uses the default batch size, 100 result entries.
To reduce the results to a manageable display size, the command is piped to the Format-Table cmdlet, where the properties Description and Source become the column headings.

### Example 2: Get events of a specific severity level
```
PS C:\>Get-SMServerEvent -Log 'Microsoft-Windows-ServerManager-DeploymentProvider/Operational' -Level Warning
```

This command returns events with a severity level of Warning from the Server Manager Deployment Provider log.

### Example 3: Get events for the File and Storage Services role
```

```

This command returns events

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

### -BatchSize
Specifies the batch size, or number of event records, that you want returned as results.
The default is 100.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CimSession
Specifies the maximum number of concurrent operations that can be established to run the cmdlet.
If this parameter is omitted or a value of `0` is entered, then Windows PowerShell® calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.
The throttle limit applies only to the current cmdlet, not to the session or to the computer.

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

### -EndTime
Specifies one or more event end times.
The time value in event records represents the number of seconds that the target server has been online.
The command omits events that occur after the *EndTime* values.

```yaml
Type: UInt64[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Level
Specifies one or more event severity levels that determine which events to return.
Valid values include

- Informational
- Error
- Warning
- Critical

If this parameter is not specified, the default is all events.

```yaml
Type: EventLevelFlag[]
Parameter Sets: (All)
Aliases:
Accepted values: Critical, Error, Warning, Informational, All

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Log
Specifies one or more Server Manager log channels.
For best results, enclose values for this parameter in single quotation marks.
The following are valid values for this parameter.

- Microsoft-Windows-ServerManager-ConfigureSMRemoting/Operational
- Microsoft-Windows-ServerManager-DeploymentProvider/Operational
- Microsoft-Windows-ServerManager-MgmtProvider/Operational
- Microsoft-Windows-ServerManager-MultiMachine/Admin
- Microsoft-Windows-ServerManager-MultiMachine/Operational

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

### -QueryFile
Specifies one or more XML query file names, used for filtering events for a specific role or feature.
To filter events for a specific role or group, first run the Get-SMServerFeature function to get the name of the query file that Server Manager uses to get data associated with a specific, installed role or feature.
The query file name becomes the value of the *QueryFile* parameter.
Note that Get-SMServerFeature does not return query file names for, nor can you get events for, roles and features that are not installed on the target server.

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

### -QueryFileId
Specifies one or more query file IDs.
You can obtain values for this parameter by running Get-SMServerFeature, as described in the preceding parameter description, *QueryFile*.

```yaml
Type: Int32[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StartTime
Specifies one or more event start times.
The time value in event records represents the number of seconds that the target server has been online.
The command omits events that occur before the *StartTime* values.

```yaml
Type: UInt64[]
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

### Microsoft.Management.Infrastructure.CimInstance#MSFT_ServerEventDetail[]

## NOTES

## RELATED LINKS

