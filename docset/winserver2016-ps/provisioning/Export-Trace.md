---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: provcmdlets.dll-Help.xml
Module Name: Provisioning
ms.date: 05/09/2017
online version: https://docs.microsoft.com/powershell/module/provisioning/export-trace?view=windowsserver2016-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Export-Trace
---

# Export-Trace

## SYNOPSIS
Exports trace events.

## SYNTAX

```
Export-Trace [-ETLFile] <String> [-Overwrite] [-LogsDirectoryPath <String>] [-WprpFile <String>]
 [-WprpFile]
```

## DESCRIPTION
Exports trace events from an event trace log (ETL) file.

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
Overwrites the existing export.

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

## INPUTS

### None


## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

