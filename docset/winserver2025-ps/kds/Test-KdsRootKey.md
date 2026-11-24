---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.KeyDistributionService.Cmdlets.dll-Help.xml
Module Name: KDS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/kds/test-kdsrootkey?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Test-KdsRootKey
---

# Test-KdsRootKey

## SYNOPSIS
Tests the root key configuration.

## SYNTAX

```
Test-KdsRootKey [-KeyId] <Guid> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Test-KdsRootKey** cmdlet tests that the root key with the specified key identifier (ID) uses a valid configuration.
The test verifies generation of both new group public key and group private key.

This cmdlet is useful for analyzing failures based on invalid root key configuration failures.

## EXAMPLES

### Example 1: Test the root key configuration
```
PS C:\> Test-KdsRootKey -KeyId 4A3615F1-5A90-22E4-0B1D-1416F93D4412
```

This command tests the configuration of the root key specified by key ID.

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

### -KeyId
Specifies the ID of the root key to test.

```yaml
Type: Guid
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
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
This cmdlet returns whether the root key can be used to generate derived keys.

## NOTES

## RELATED LINKS

[Add-KdsRootKey](./Add-KdsRootKey.md)

[Clear-KdsCache](./Clear-KdsCache.md)

[Get-KdsConfiguration](./Get-KdsConfiguration.md)

[Set-KdsConfiguration](./Set-KdsConfiguration.md)

[Add-KdsRootKey](./Add-KdsRootKey.md)

