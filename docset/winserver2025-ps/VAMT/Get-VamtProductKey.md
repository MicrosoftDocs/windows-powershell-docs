---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Licensing.VolumeActivation.Powershell.dll-Help.xml
Module Name: VAMT
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/vamt/get-vamtproductkey?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-VamtProductKey
---

# Get-VamtProductKey

## SYNOPSIS
Retrieves product-key records from a VAMT database.

## SYNTAX

```
Get-VamtProductKey [-DbConnectionString <String>] [-DbCommandTimeout <Int32>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-VamtProductKey** cmdlet retrieves product key records from a dep_nextref_vamt database.
You can use this cmdlet to retrieve a single product key or a list of product keys.
The results are saved to a file, or a **Microsoft.Licensing.VolumeActivation.Product** object is returned.

## EXAMPLES

### Example 1: Get MAK keys
```
PS C:\>$MakKeys = Get-VamtProductKey | where { $_.keytype -eq 'mak' }
```

This command gets a list of MAK keys.

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
Specifies the database that the product key or list of product keys is retrieved from.
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Add-VamtProductKey](./Add-VamtProductKey.md)

[Install-VamtProductKey](./Install-VamtProductKey.md)

