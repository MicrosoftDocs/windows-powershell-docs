---
author: Kateyanne
external help file: SMTasks_Cmdlets.xml
manager: dansimp
Module Name: ServerManagerTasks
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/servermanagertasks/get-smserverevent?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-SMServerEvent

## SYNOPSIS
Gets the details of events generated in one or more event logs by log file name or event query.

## SYNTAX

```
Get-SMServerEvent [-AsJob] [-BatchSize <UInt32>] [-CimSession <CimSession[]>] [-EndTime <UInt64[]>]
 [-Level <EventLevelFlag[]>] [-Log <String[]>] [-QueryFile <String[]>] [-QueryFileId <Int32[]>]
 [-StartTime <UInt64[]>] [-ThrottleLimit <Int32>]
```

## DESCRIPTION
The **Get-SMServerEvent** cmdlet gets the details of events in one or more event logs by log file name or event query.
Windows Server generates log entries for application, security, system, setup, and forwarded events.

## EXAMPLES

### Example 1:Get server events
```
PS C:\>Get-SMServerEvent -Level @(7)-Log @('Application') -ThrottleLimit 16
```

This command gets the critical, error, and warning events in the application log, and specifies a throttle limit value of 16.

## PARAMETERS

### -AsJob
ps_cimcommon_asjob

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
Specifies the batch size that the command uses to stream results.
If you do not specify a value, the command defaults to 256.

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
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EndTime
Specifies an array of end times.The command omits events that occur after the *EndTime*.

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
Specifies an array of **EventLevelFlags** that determines which events to return.

The event level flag values and names are: 

    --Value=1 Name=Critical

    --Value=2 Name=Error 

    --Value=4 Name=Warning 

    --Value=8 Name=Informational 

    --Value=16 Name=All

```yaml
Type: EventLevelFlag[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Log
Specifies an array of log files.

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
Specifies an array of query file names.

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
Specifies an array of query file IDs.

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
Specifies an array of start times for events.
The command omits events that occur before the *StartTime*

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

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#MSFT_ServerEventDetail[]

## NOTES

## RELATED LINKS



