---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Licensing.VolumeActivation.Powershell.dll-Help.xml
Module Name: VAMT
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/vamt/update-vamtproduct?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Update-VamtProduct
---

# Update-VamtProduct

## SYNOPSIS
Updates the VAMT database by querying the computers for their current status.

## SYNTAX

```
Update-VamtProduct -Products <Product[]> [-DbConnectionString <String>] [-Username <String>]
 [-Password <String>] [-DbCommandTimeout <Int32>] [<CommonParameters>]
```

## DESCRIPTION
The **Update-VamtProduct** cmdlet updates the information in the dep_nextref_vamt database by querying the computers in the environment for their current status.
You can use this cmdlet in a script when product data in the database must be updated regularly.

## EXAMPLES

### Example 1: Update all product information in database
```
PS C:\>Get-VamtProduct | Update-VamtProduct
```

This command updates all of the product information in the database.

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
Specifies the database where the products are updated.
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

### -Password
Provides the password for password-protected environments.

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

### -Products
Specifies the product or products in the dep_nextref_vamt database that this cmdlet updates.

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

### -Username
Provides the user name for password-protected environments.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-VamtProduct](./Get-VamtProduct.md)

