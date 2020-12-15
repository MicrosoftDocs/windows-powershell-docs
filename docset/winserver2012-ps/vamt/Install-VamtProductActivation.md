---
external help file: VAMT_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: 5B87C8DB-4B08-4C82-BBB9-E17C75EFB79D
manager: dansimp
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

