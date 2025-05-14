---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Licensing.VolumeActivation.Powershell.dll-Help.xml
Module Name: VAMT
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/vamt/get-vamtproduct?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-VamtProduct
---

# Get-VamtProduct

## SYNOPSIS
Retrieves the record of a product or list of products from a VAMT database.

## SYNTAX

```
Get-VamtProduct [-DbConnectionString <String>] [-ProductName <String>] [-DbCommandTimeout <Int32>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-VamtProduct** cmdlet retrieves the record of a product or list of products from a dep_nextref_vamt database.
The results are saved to a file, or a **Microsoft.Licensing.VolumeActivation.Product** object is returned.

## EXAMPLES

### Example 1: Save all products in a file
```
PS C:\>Get-VamtProduct > c:\users\me\windowslist.txt
```

This command outputs the list of all products in the dep_nextref_vamt database to the specified file.

### Example 2: Get all Windows products that are not licensed
```
PS C:\>$Products = Get-VamtProduct -ProductName "windows" | where { $_.licensestatus -ne 'Licensed' }
```

This command returns all Windows products whose license status does not equal licensed.

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
Specifies the database that the product or list of products are retrieved from.
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
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -ProductName
Specifies the product information to retrieve.
If the *ProductName* parameter is not included, dep_nextref_vamt retrieves all product information in the dep_nextref_vamt database.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
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

[Update-VamtProduct](./Update-VamtProduct.md)

