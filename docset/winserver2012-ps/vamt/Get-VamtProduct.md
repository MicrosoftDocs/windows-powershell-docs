---
author: Kateyanne
external help file: VAMT_Cmdlets.xml
manager: dansimp
Module Name: VAMT
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/vamt/get-vamtproduct?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-VamtProduct

## SYNOPSIS
Retrieves the record of a product or list of products from a VAMT database.

## SYNTAX

```
Get-VamtProduct [[-ProductName] <String>] [-DbCommandTimeout <Int32>] [-DbConnectionString <String>]
```

## DESCRIPTION
The **Get-VamtProduct** cmdlet retrieves the record of a product or list of products from a dep_nextref_vamt database.
The results are saved to a file, or a Microsoft.Licensing.VolumeActivation.Product object is returned.

## EXAMPLES

### Example 1
```
PS C:\>get-vamtproduct > c:\users\me\windowslist.txt
```

This command outputs the list of all products in the dep_nextref_vamt database to the specified file.

### Example 2
```
PS C:\>$products = get-vamtproduct -productname windows | where { $_.licensestatus -ne 'Licensed' }
```

This command returns all "Windows" products whose license status does not equal "licensed".

## PARAMETERS

### -DbCommandTimeout
Indicates how long dep_nextref_vamt waits for a response from the database before timing out.
The default value is 30 seconds.
You can use the *DbCommandTimeout* parameter to change the timeout value.

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
Accept pipeline input: True (ByValue, ByPropertyName)
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
Position: 1
Default value: None
Accept pipeline input: True (ByValue, ByPropertyName)
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Update-VamtProduct](./Update-VamtProduct.md)

