---
external help file: Microsoft.Protocols.Tools.PowerShell.dll-Help.xml
Module Name: PEF
ms.date: 10/30/2017
online version: https://docs.microsoft.com/powershell/module/pef/add-pefmessagesource?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-PefMessageSource
---

# Add-PefMessageSource

## SYNOPSIS
Adds message sources to a PEF Trace Session.

## SYNTAX

```
Add-PefMessageSource [-PEFSession] <IPpkTraceSession> [-Source] <Object[]> [-LogConfiguration <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Add-PefMessageSource** cmdlet adds message sources to a Trace Session.
You can specify a file containing message data as a source or use Event Tracing for Windows (ETW) providers for a Protocol Engineering Framework (PEF) Live Trace Session.

## EXAMPLES

### Example 1: Add a trace file as a message source for a Trace Session
```
C:\PS> $TraceSession01 = New-PefTraceSession
C:\PS> Add-PefMessageSource -PEFSession $TraceSession01 -Source "C:\Captures\UDP10k.cap"
C:\PS> Start-PefTraceSession -PEFSession $TraceSession01
```

The first command creates a PEF Trace Session object, and then stores it in the **$TraceSession01** variable.

The second command adds a saved Microsoft Network Monitor capture file (.cap) as the message source for the Trace Session stored in the **$TraceSession01** variable.

The final command starts the Trace Session stored in the **$TraceSession01** variable.

### Example 2: Add a PEF message provider to a Trace Session
```
C:\PS> $TraceSession01 = New-PefTraceSession
C:\PS> Add-PefMessageSource -PEFSession $TraceSession01 -Source "Microsoft-Pef-WFP-MessageProvider"
C:\PS> Start-PefTraceSession -PEFSession $TraceSession01
```

The first command creates a PEF Trace Session object, and then stores it in the **$TraceSession01** variable.

The second command adds the Microsoft-Pef-WFP-MessageProvider as the provider for the Trace Session object stored in the **$TraceSession01** variable.

The final command starts the Trace Session stored in the **$TraceSession01** variable.

### Example 3: Add a manifest-based ETW provider to a Trace Session
```
C:\PS> $TraceSession01 = New-PefTraceSession
C:\PS> Add-PefMessageSource -PEFSession $TraceSession01 -Source "Microsoft-Windows-Dhcp-Client"
C:\PS> Start-PefTraceSession -PEFSession $TraceSession01
```

The first command creates a PEF Trace Session object, and then stores it in the **$TraceSession01** variable.

The second command adds the Microsoft-Windows-Dhcp-Client system ETW provider to the Trace Session object stored in the **$TraceSession01** variable.

The final command starts the Trace Session stored in the **$TraceSession01** variable.

### Example 4: Add a text log file as a message source for a Live Trace Session
```
C:\PS> $TraceSession01 = New-PefTraceSession
C:\PS> Add-PefMessageSource -PEFSession $TraceSession01 -Provider "C:\Captures\IIS.log" -LogConfig IIS
C:\PS> Start-PefTraceSession -PEFSession $TraceSession01
```

The first command creates a PEF Trace Session object, and then stores it in the **$TraceSession01** variable.

The second command adds a saved IIS text log as the message source for the Trace Session stored in **$TraceSession01** and uses the **LogConfig** parameter to specify the configuration file that is required to parse the log.

The final command starts the Trace Session stored in **$TraceSession01**.

## PARAMETERS

### -LogConfiguration
Specifies the text log configuration file to use to parse the source data.
Specify this parameter if you use text log files as a message source.

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

### -PEFSession
Specifies an object that contains a Trace Session. 
To create a Trace Session, use the New-PefTraceSession cmdlet.
This cmdlet adds message sources to the session object that this parameter specifies.

```yaml
Type: IPpkTraceSession
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Source
Specifies an array of message provider names.

```yaml
Type: Object[]
Parameter Sets: (All)
Aliases: Provider

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[New-PefTraceSession](./New-PefTraceSession.md)

[Start-PefTraceSession](./Start-PefTraceSession.md)

