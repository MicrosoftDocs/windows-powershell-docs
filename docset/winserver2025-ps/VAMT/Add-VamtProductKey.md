---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Licensing.VolumeActivation.Powershell.dll-Help.xml
Module Name: VAMT
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/vamt/add-vamtproductkey?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-VamtProductKey
---

# Add-VamtProductKey

## SYNOPSIS
Adds the user-specified product key to a VAMT database.

## SYNTAX

```
Add-VamtProductKey -ProductKey <String> [-DbConnectionString <String>] [-DbCommandTimeout <Int32>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Add-VamtProductKey** cmdlet adds the user-specified product key to a dep_firstref_vamt database.
If a list of product keys must be added to a dep_nextref_vamt database, you can use this cmdlet in a script to add the product keys.

## EXAMPLES

### Example 1: Add a product key to a database
```
PS C:\> add-vamtproductkey -ProductKey "12345-456789-12345-456789-12345" -DbConnectionString "data source=.\adk;initial catalog=test;integrated security=true;multipleactiveresultsets=true"
```

This command adds a product key to the specified dep_nextref_vamt database.

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
Specifies the database that the product key is added to.
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

### -ProductKey
Specifies the product key to be added to the dep_nextref_vamt database.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-VamtProductKey](./Get-VamtProductKey.md)

[Install-VamtProductKey](./Install-VamtProductKey.md)

