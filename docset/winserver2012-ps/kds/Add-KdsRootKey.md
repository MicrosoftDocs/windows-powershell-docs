---
external help file: Microsoft.KeyDistributionService.Cmdlets.dll-Help.xml
ms.assetid: 2E649F25-5050-492D-8A49-662B73B4C7B5
manager: dansimp
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: kenwith
author: kenwith
---

# Add-KdsRootKey

## SYNOPSIS
Generates a new root key for the Microsoft Group Key Distribution Service (KdsSvc) within Active Directory (AD).

## SYNTAX

### EffectiveTime (Default)
```powershell
Add-KdsRootKey [-LocalTestOnly] [[-EffectiveTime] <DateTime>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### EffectiveImmediately
```powershell
Add-KdsRootKey [-LocalTestOnly] [-EffectiveImmediately] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Add-KdsRootKey** cmdlet generates a new root key for the Microsoft Group Key Distribution Service (KdsSvc) within Active Directory (AD).
The Microsoft Group KdsSvc generates new group keys from the new root key.

## EXAMPLES

### Example 1: Generate a new root key
```powershell
PS C:\>Add-KdsRootKey
```

This example generates a new root key for the Microsoft Group KdsSvc within AD.

### Example 2: Generate a new root key for immediate use
```powershell
PS C:\>Add-KdsRootKey -EffectiveImmediately
```

This example generates a new root key and will be usable after 10 hours of creation and adds it to the Microsoft Group KdsSvc.

>[!NOTE]
>There is a 10 hour waiting period from creation, to allow all DCs to converge with AD replication, before you can create gMSA. This prevents password generation before all DCs in the environment have answered the gMSA request.

>[!TIP] For inmediate use please use:
>```Powershell 
>Add-KdsRootKey –EffectiveTime ((get-date).addhours(-10))  
>``` 
>*Allows using gMSAs **immediately**, because it sets the start time 10 hours in past.*

### Example 3: Generate a new root key which takes effect on a specific date
```powershell
PS C:\>Add-KdsRootKey -EffectiveTime "03/06/2013"
```

This example generates a new root key for the Microsoft Group KdsSvc which takes effect on the specified date 03/06/2013 using the mm/dd/yyyy format.

### Example 4: Generate a new root key on the local host only
```powershell
PS C:\>Add-KdsRootKey -LocalTestOnly
```

This example generates a new root key on the local host only.

## PARAMETERS

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -EffectiveImmediately
Indicates that the Microsoft Group Key Distribution Service immediately uses the new root key.

```yaml
Type: SwitchParameter
Parameter Sets: EffectiveImmediately
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EffectiveTime
Specifies the date on which the newly generated root key takes effect.
If this parameter is not specified, the default date set is 10 days after the current date.

```yaml
Type: DateTime
Parameter Sets: EffectiveTime
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -LocalTestOnly
Indicates that the new root key is generated on the local host only.
This parameter is used with the Set-KdsConfigurationSet-KdsConfiguration cmdlet to test the local server configuration. 

If this parameter is specified, then the cmdlet returns a value that indicates whether the test passed. 

If this parameter is not specified, then the cmdlet returns the identifier (ID) of the root key when the operation succeeds.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None
This cmdlet accepts no input objects.

## OUTPUTS

### System.Boolean

### System.Guid

## NOTES

## RELATED LINKS

[Clear-KdsCache](./Clear-KdsCache.md)

[Get-KdsConfiguration](./Get-KdsConfiguration.md)

[Get-KdsRootKey](./Get-KdsRootKey.md)

[Set-KdsConfiguration](./Set-KdsConfiguration.md)

[Test-KdsRootKey](./Test-KdsRootKey.md)

