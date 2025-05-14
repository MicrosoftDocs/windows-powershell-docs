---
description: The Export-Trace cmdlet exports an event trace log (ETL) file for provisioning.
external help file: provcmdlets.dll-Help.xml
Module Name: Provisioning
ms.date: 05/09/2017
online version: https://learn.microsoft.com/powershell/module/provisioning/export-trace?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Export-Trace
---

# Export-Trace

## SYNOPSIS
Exports an event trace log file for provisioning.

## SYNTAX

```
Export-Trace [-ETLFile] <String> [-Overwrite] [-LogsDirectoryPath <String>] [-WprpFile <String>]
 [-ConnectedDevice] [<CommonParameters>]
```

## DESCRIPTION
Exports trace events from an event trace log ETL file.

## EXAMPLES

### Example 1: Export trace events from an ETL file
```powershell
PS C:\> Export-Trace -ETLFile C:\Windows\Logs\WindowsUpdate\WindowsUpdate.20211013.074054.819.1.etl -LogsDirectoryPath C:\ETL\Logs
```

Exports trace events from a specified ETL file and saves the logs to the C:\ETL\Logs folder.

## PARAMETERS

### -ConnectedDevice
If enabled, specifies that the device type is mobile.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: Device

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ETLFile
Specifies the ETL file location.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Etl

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LogsDirectoryPath
Specifies the logs directory path.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Logs

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Overwrite
Indicates that the cmdlet overwrites an existing exported log if one exists.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: Force, Overwrite

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WprpFile
Specifies the location of the WPR profile file.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Wprp

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None
## OUTPUTS

### System.Object
## NOTES

## RELATED LINKS
