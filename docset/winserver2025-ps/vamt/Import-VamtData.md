---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Licensing.VolumeActivation.Powershell.dll-Help.xml
Module Name: VAMT
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/vamt/import-vamtdata?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Import-VamtData
---

# Import-VamtData

## SYNOPSIS
Imports the data from a specified .cilx or .cil file into a VAMT database.

## SYNTAX

### Products
```
Import-VamtData -Products <Product[]> [-DbConnectionString <String>] [-DbCommandTimeout <Int32>]
 [<CommonParameters>]
```

### File
```
Import-VamtData -InputFile <String> [-DbConnectionString <String>] [-DbCommandTimeout <Int32>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Import-VamtData** cmdlet imports data from a specified .cilx or .cil file into a dep_nextref_vamt database.
You can merge data from a previous version of dep_nextref_vamt into your database by exporting the data in the previous version to a .cil file and then importing the .cil file into the dep_nextref_vamt database.
You can import data from a .cilx file to recover data from a backup file.

## EXAMPLES

### Example 1: Import data from a file
```
PS C:\> Import-VamtData -InputFile ".\vamtdata.cilx"
```

This command imports data from the specified file.

### Example 2: Get and import data
```
PS C:\> $ProductInfo = Get-VamtProduct
PS C:\> $UpdatedProductInfo = Get-VamtConfirmationId -Products $productinfo
PS C:\> Import-VamtData -Products $UpdatedProductInfo
```

This command gets a product object, acquires the confirmation IDs for the products, and then imports the data to the database.
Just acquiring the CIDs does not mean that the data is in the database.
The data must be imported as shown in this example.

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
Specifies the database that the data from the .cilx file or .cil file is imported into.
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

### -InputFile
Specifies the name of the file that contains the data to import into the dep_nextref_vamt database.
You cannot use the *InputFile* parameter together with the *Products* parameter.

```yaml
Type: String
Parameter Sets: File
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Products
Specifies the product information to import.
If the *Products* parameter is not included, all product information in the .cilx or .cil file is imported into the dep_nextref_vamt database.
You cannot use the *Products* parameter together with the *InputFile* parameter.

```yaml
Type: Product[]
Parameter Sets: Products
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

[Get-VamtConfirmationId](./Get-VamtConfirmationId.md)

[Get-VamtProduct](./Get-VamtProduct.md)

[Export-VamtData](./Export-VamtData.md)

[Initialize-VamtData](./Initialize-VamtData.md)

