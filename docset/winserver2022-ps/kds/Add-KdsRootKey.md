---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.KeyDistributionService.Cmdlets.dll-Help.xml
Module Name: KDS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/kds/add-kdsrootkey?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-KdsRootKey
---

# Add-KdsRootKey

## SYNOPSIS
Generates a new root key for the Microsoft Group KdsSvc within Active Directory.

## SYNTAX

### EffectiveTime (Default)
```
Add-KdsRootKey [-LocalTestOnly] [[-EffectiveTime] <DateTime>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### EffectiveImmediately
```
Add-KdsRootKey [-LocalTestOnly] [-EffectiveImmediately] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Add-KdsRootKey** cmdlet generates a new root key for the Microsoft Group Key Distribution Service (KdsSvc) within Active Directory.
The Microsoft Group KdsSvc generates new group keys from the new root key. It is required to run this only once per forest.

## EXAMPLES

### Example 1: Generate a new root key
```
PS C:\> Add-KdsRootKey
```

This command generates a new root key for the Microsoft Group KdsSvc within Active Directory.

### Example 2: Generate a new root key for immediate use
```
PS C:\> Add-KdsRootKey -EffectiveImmediately
```

This command generates a new root key immediately and adds it to the Microsoft Group KdsSvc.

### Example 3: Generate a new root key which takes effect on a specific date
```
PS C:\> Add-KdsRootKey -EffectiveTime 03/23/2013
```

This command generates a new root key for the Microsoft Group KdsSvc which takes effect on the date 03/23/2013.
Use the mm/dd/yyyy format.

### Example 4: Generate a new root key on the local host only
```
PS C:\> Add-KdsRootKey -LocalTestOnly
```

This command generates a new root key on the local host only.

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
This parameter is used with the **Set-KdsConfiguration** cmdlet to test the local server configuration.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

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

