---
external help file: Microsoft.Protocols.Tools.PowerShell.dll-Help.xml
Module Name: PEF
ms.date: 10/30/2017
online version: https://docs.microsoft.com/powershell/module/pef/new-peftracesession?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-PefTraceSession
---

# New-PefTraceSession

## SYNOPSIS
Creates a PEF Trace Session.

## SYNTAX

```
New-PefTraceSession [[-Mode] <PEFSessionMode>] [[-Filter] <String>] [-Name <String>] [-SaveOnStop]
 [-SaveAsParsed] [-Silent] [<CommonParameters>]
```

## DESCRIPTION
The **New-PefTraceSession** cmdlet creates a Protocol Engineering Framework (PEF) Trace Session to capture live data or to load message data from saved trace files or logs.
This cmdlet enables you to specify a mode, either Circular or Linear, to control how much data the Trace Session holds.
You can also specify a filter that selects specific types of messages during data retrieval, either from a Live Trace Session or from saved files and logs.
Use the **SaveOnStop** parameter to save a data collection to a file when the Trace Session stops.

You can use the Add-PefMessageSource cmdlet to specify a message provider for a capture session.

After you create a Trace Session object, use the Start-PefTraceSession and Stop-PefTraceSession cmdlets to define how the session will start and stop collecting message data.

You need to be a member of the Message Capture Users Group and the Performance Log Users Group.

## EXAMPLES

### Example 1: Create and run a PEF Trace Session
```
PS C:\> $TraceSession01 = New-PefTraceSession -Mode Circular -Force -Path "C:\Traces\Trace01.matu" -TotalSize 50 -SaveOnStop
PS C:\> Add-PefMessageSource -PEFSession $TraceSession01 -Source "Microsoft-Pef-WFP-MessageProvider"
PS C:\> Start-PefTraceSession -PEFSession $TraceSession01
```

This example creates and starts a PEF Trace Session.

The first command creates a Trace Session object and stores it in the **$TraceSession01** variable.
This command specifies the Circular capture mode, with a total size of 50 MB.
The command also uses the **SaveOnStop** parameter and specifies a name for the trace file Trace01.matu, by using the **Path** parameter, which saves the Trace Session results in the current directory.
The command uses the **Force** parameter, which causes any existing file of the same name to be overwritten when your Trace Session results are saved.

The second command uses the Add-PefMessageSource cmdlet to specify a provider for the Trace Session stored in the **$TraceSession01** variable.

The final command uses the Start-PefTraceSession cmdlet to start the Trace Session stored in **$TraceSession01**.

## PARAMETERS

### -Filter
Specifies a string that configures a Trace Filter, which defines the types of messages that a Trace Session retrieves.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Mode
Specifies a mode for the Trace Session.
The acceptable values for this parameter are:

- Circular.
The Trace Session records data until the data size reaches a limit defined by the **TotalSize** dynamic parameter, and then the session records new data while discarding the oldest recorded data. 
- Linear.
The session does not discard data.

The default value for this parameter is Linear.

```yaml
Type: PEFSessionMode
Parameter Sets: (All)
Aliases: 
Accepted values: Linear, Circular

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies an input file path.
If you use the **SaveOnStop** parameter, you can specify this parameter to cause the Trace Session to retrieve input data from the specified file.

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

### -SaveAsParsed
Indicates that the cmdlet parses all messages fully, and saves them as a .matp file.
By default, the cmdlet saves trace data as unparsed.
The parsed data in a .matp file loads more quickly.
The operation of parsing during capture causes the cmdlet to capture data more slowly.

If you specify the Circular value for the **Mode** parameter, you should not specify the **SaveAsParsed** parameter.

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

### -SaveOnStop
Indicates that the Trace Session saves data when it stops.
You can use the **Name** dynamic parameter to specify a file path for saving the data.

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

### -Silent
Indicates that the cmdlet shows no output.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Start-PefTraceSession](./Start-PefTraceSession.md)

[Stop-PefTraceSession](./Stop-PefTraceSession.md)

[Add-PefMessageSource](./Add-PefMessageSource.md)

[New-PefKeyDownTrigger](./New-PefKeyDownTrigger.md)

