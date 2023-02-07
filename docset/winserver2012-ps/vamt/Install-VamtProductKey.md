---
external help file: VAMT_Cmdlets.xml
Module Name: VAMT
online version: https://learn.microsoft.com/powershell/module/vamt/install-vamtproductkey?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Install-VamtProductKey

## SYNOPSIS
Installs the specified product key on a product or a group of products.

## SYNTAX

```
Install-VamtProductKey [-Products] <Product[]> [-ProductKey] <String> [[-Username] <String>]
 [[-Password] <String>] [-DbCommandTimeout <Int32>] [-DbConnectionString <String>]
```

## DESCRIPTION
The **Install-VamtProductKey** cmdlet installs the specified product key on a single product or on a group of products.
The cmdlet returns a value to indicate whether the product key is valid.

## EXAMPLES

### Example
```
PS C:\> $product = get-vamtproduct | where { $_.fullyqualifieddomainname -eq 'mymachine' }
PS C:\> install-vamtproductkey $product -productkey 12345-67890-12345-67890-12345
```

This command gets a specified product by using the fully qualified domain name and then installs the specified product key on that product.

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
Specifies the database where the product keys are installed.
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
Provides a password for password-protected environments.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 5
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ProductKey
Specifies the product key to be installed on the product or products.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByValue, ByPropertyName)
Accept wildcard characters: False
```

### -Products
Specifies the product or products that the product key will be installed on.

```yaml
Type: Product[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue, ByPropertyName)
Accept wildcard characters: False
```

### -Username
Provides a user name for password-protected environments.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-VamtProductKey](./Get-VamtProductKey.md)

[Add-VamtProductKey](./Add-VamtProductKey.md)

