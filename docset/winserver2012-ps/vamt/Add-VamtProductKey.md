---
external help file: VAMT_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: 3868B8D4-2230-4A70-B4FD-CCA4F53DC0A1
manager: dansimp
---

# Add-VamtProductKey

## SYNOPSIS
Adds the user-specified product key to a VAMT database.

## SYNTAX

```
Add-VamtProductKey [-ProductKey] <String> [-DbCommandTimeout <Int32>] [-DbConnectionString <String>]
```

## DESCRIPTION
The Add-VamtProductKey cmdlet adds the user-specified product key to a dep_firstref_vamt database.
If a list of product keys must be added to a dep_nextref_vamt database, you can use this cmdlet in a script to add the product keys.

## EXAMPLES

### Example
```
PS C:\> add-vamtproductkey -productkey 12345-456789-12345-456789-12345 -dbConnectionstring "data source=.\adk;initial catalog=test;integrated security=true;multipleactiveresultsets=true"
```

This command adds a product key to the specified dep_nextref_vamt database.

## PARAMETERS

### -DbCommandTimeout
Indicates how long dep_nextref_vamt waits for a response from the database before timing out.
The default value is 30 seconds.
You can use the DbCommandTimeout parameter to change the timeout value.

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
Position: 1
Default value: None
Accept pipeline input: True (ByValue, ByPropertyName)
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-VamtProductKey](./Get-VamtProductKey.md)

[Install-VamtProductKey](./Install-VamtProductKey.md)

