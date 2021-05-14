---
external help file: VAMT_Cmdlets.xml
Module Name: VAMT
online version: https://docs.microsoft.com/powershell/module/vamt/import-vamtdata?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Import-VamtData

## SYNOPSIS
Imports the data from a specified .cilx or .cil file into a VAMT database.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Import-VamtData [-InputFile] <String> [-DbCommandTimeout <Int32>] [-DbConnectionString <String>]
```

### UNNAMED_PARAMETER_SET_2
```
Import-VamtData [-Products] <Product[]> [-DbCommandTimeout <Int32>] [-DbConnectionString <String>]
```

## DESCRIPTION
The **Import-VamtData** cmdlet imports data from a specified .cilx or .cil file into a dep_nextref_vamt database.
You can merge data from a previous version of dep_nextref_vamt into your database by exporting the data in the previous version to a .cil file and then importing the .cil file into the dep_nextref_vamt database.
You can import data from a .cilx file to recover data from a backup file.

## EXAMPLES

### Example 1
```
PS C:\> import-vamtdata -inputfile .\vamtdata.cilx
```

This command imports data from the specified file.

### Example 2
```
PS C:\> $productinfo = get-vamtproduct
PS C:\> $updatedproductinfo = get-vamtconfirmationid -products $productinfo
PS C:\> import-vamtdata -products $updatedproductinfo
```

This command gets a product object, acquires the confirmation IDs for the products, and then imports the data to the database.
Just acquiring the CIDs does not mean that the data is in the database.
The data must be imported as shown in this example.

## PARAMETERS

### -DbCommandTimeout
Indicates how long dep_nextref_vamt waits for a response from the database before timing out.
The default value is 30 seconds.
You can use the **DbCommandTimeout** parameter to change the timeout value.

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
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue, ByPropertyName)
Accept wildcard characters: False
```

### -Products
Specifies the product information to import.
If the *Products* parameter is not included, all product information in the .cilx or .cil file is imported into the dep_nextref_vamt database.
You cannot use the *Products* parameter together with the *InputFile* parameter.

```yaml
Type: Product[]
Parameter Sets: UNNAMED_PARAMETER_SET_2
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

[Export-VamtData](./Export-VamtData.md)

[Initialize-VamtData](./Initialize-VamtData.md)

