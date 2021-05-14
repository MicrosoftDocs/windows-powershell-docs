---
external help file: VAMT_Cmdlets.xml
Module Name: VAMT
online version: https://docs.microsoft.com/powershell/module/vamt/install-vamtproductactivation?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Install-VamtProductActivation

## SYNOPSIS
Activates products online, using the local computer's Internet connection.

## SYNTAX

```
Install-VamtProductActivation [-Products] <Product[]> [[-Username] <String>] [[-Password] <String>]
```

## DESCRIPTION
The **Install-VamtProductActivation** cmdlet activates products online by using the Internet connection on the local computer.
You cannot use this cmdlet for proxy activation.

## EXAMPLES

### Example
```
PS C:\>get-vamtproduct | install-vamtproductactivation
```

This command gets products and then activates them by using online activation.

## PARAMETERS

### -Password
Provides a password for password-protected environments.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Products
Specifies the product or products to be activated.

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
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

