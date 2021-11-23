---
description: The Export-Trace cmdlet exports an event trace log (ETL) file for provisioning.
external help file: provcmdlets.dll-Help.xml
Module Name: Provisioning
ms.date: 05/09/2017
online version: https://docs.microsoft.com/powershell/module/provisioning/export-trace?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
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
The **Export-Trace** cmdlet exports an event trace log (ETL) file for provisioning.

The **Export-Trace** cmdlet is supported on Windows 11 client operating system only.

## EXAMPLES

### Example 1
```
Export-Trace -ETLFile C:\Windows\Logs\provisioning.etl -Overwrite
```

This example exports an ETL file to the specified location, overwriting an existing file, if it exists.

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
Specifies a location for the .etl file.

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
Specifies the path of the logs directory.

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
