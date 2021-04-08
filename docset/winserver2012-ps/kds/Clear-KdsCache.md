---
author: Kateyanne
external help file: Microsoft.KeyDistributionService.Cmdlets.dll-Help.xml
manager: dansimp
Module Name: KDS
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/kds/clear-kdscache?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Clear-KdsCache

## SYNOPSIS
Clears the group key cache of the local computer.

## SYNTAX

```
Clear-KdsCache [-CacheOwnerSid <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Clear-KdsCache** cmdlet clears the group key cache of the local computer.

The local computer can be either a domain controller running the Microsoft Group Key Distribution Service (KdsSvc) or a client of the Microsoft Group KdsSvc.

## EXAMPLES

### Example 1: Clear the group key cache
```
PS C:\>Clear-KdsCache
```

This example clears the group key cache of the local computer.

### Example 2: Clear the group key cache of a specific user
```
PS C:\>Clear-KdsCache -CacheOwnerSid "s-1-1-0"
```

This example clears the group key cache of the user with SID s-1-1-0.

## PARAMETERS

### -CacheOwnerSid
Specifies the security identifier (SID) for the user account whose cache this cmdlet clears.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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

### None
This cmdlet produces no output.

## NOTES

## RELATED LINKS

[Add-KdsRootKey](./Add-KdsRootKey.md)

[Get-KdsConfiguration](./Get-KdsConfiguration.md)

[Get-KdsRootKey](./Get-KdsRootKey.md)

[Set-KdsConfiguration](./Set-KdsConfiguration.md)

[Test-KdsRootKey](./Test-KdsRootKey.md)

