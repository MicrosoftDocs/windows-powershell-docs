---
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
ms.assetid: 56F8DEDD-69B2-42D9-B55C-C83208EBBA8E
manager: dansimp
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: kenwith
author: kenwith
---

# Enable-WebRequestTracing

## SYNOPSIS
Enables Request Tracing for the site specified.

## SYNTAX

```
Enable-WebRequestTracing [[-Name] <String>] [-Directory <String>] [-MaxLogFiles <UInt32>]
 [-MaxLogFileSize <UInt32>] [-CustomActions] [-StatusCodes <String>] [<CommonParameters>]
```

## DESCRIPTION
This cmdlet enables Request Tracing, and automatically configures a site rule that traces responses that have a status value between 400 and 600.

## EXAMPLES

### -------------- EXAMPLE 1: Enabling Request Tracing for the "Default Web Site" --------------
```
IIS:\>Enable-WebRequestTracing -Name "Default Web Site"
```

Enables Request Tracing for the Default Web Site, which also automatically creates a rule that traces status code 500 errors.

## PARAMETERS

### -CustomActions
Specifies an action taken when a Request Tracing log file is generated.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Directory
The directory in which Request Tracing log files are stored.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MaxLogFileSize
The maximum file size of a single Request Tracing log file.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MaxLogFiles
The maximum number of log files to store.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
The name of the site for which tracing is enabled.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StatusCodes
Status codes for which a default Request Tracing rule is configured.
The default code value is 500.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Disable-WebRequestTracing](./Disable-WebRequestTracing.md)

