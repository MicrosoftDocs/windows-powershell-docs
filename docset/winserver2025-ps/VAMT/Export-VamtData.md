---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Licensing.VolumeActivation.Powershell.dll-Help.xml
Module Name: VAMT
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/vamt/export-vamtdata?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Export-VamtData
---

# Export-VamtData

## SYNOPSIS
Exports product data and product-key data from a VAMT database to a portable .cilx file.

## SYNTAX

```
Export-VamtData -Products <Product[]> -OutputFile <String> [-DbConnectionString <String>] [-IncludeProductKeys]
 [-IncludeSensitiveInfo] [-DbCommandTimeout <Int32>] [<CommonParameters>]
```

## DESCRIPTION
The **Export-VamtData** cmdlet exports specified product data and product-key data from a dep_firstref_vamt database to a portable cilx file.
You can use this .cilx file to move data from one dep_nextref_vamt instance to another, to store data for backup purposes, or to facilitate proxy activation.
By default, the export does not include product-key data and personally identifiable information (PII).

## EXAMPLES

### Example 1: Export data to a file
```
PS C:\>Get-VamtProduct | Export-VamtData -IncludeProductKeys -IncludeSensitiveInfo -outputfile "c:\users\me\desktop\vamtdata.cilx"
```

This command gets a dep_nextref_vamt product object that contains all products and then exports the object to the specified file.
The command also specifies to include product keys and personally identifiable information.

## PARAMETERS

### -DbCommandTimeout
Indicates how long dep_nextref_vamt waits for a response from the database before timing out.
The default value is 30 seconds.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DbConnectionString
Specifies the database that the product and the product key are exported from.
If no database connection string is provided, dep_nextref_vamt attempts to use the database that the dep_nextref_vamt user console used on the local computer.
If dep_nextref_vamt does not find a database, it returns an error.
You can find the connection string in the dep_nextref_vamt UI in the Preferences dialog box.
On the menu bar, click View, and then click Preferences to open the Volume Activation Management Tool Preferences dialog box.
The connection string is in the Database Settings section under Current connection string.

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

### -IncludeProductKeys
Indicates that this cmdlet includes product keys in the export.
By default, dep_nextref_vamt does not include product keys in the export.

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

### -IncludeSensitiveInfo
Indicates that this cmdlet includes personally identifiable information (PII) in the export.
By default, dep_nextref_vamt does not include PII in the export.

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

### -OutputFile
Specifies the location and name of the .cilx file that this cmdlet creates.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Products
Specifies the product information to be exported.
If the *Products* parameter is not included, dep_nextref_vamt exports all product information in the dep_nextref_vamt database to the .cilx file.

```yaml
Type: Product[]
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Import-VamtData](./Import-VamtData.md)

[Initialize-VamtData](./Initialize-VamtData.md)

