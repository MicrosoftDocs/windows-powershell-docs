---
external help file: Microsoft.IdentityServer.PowerShell.dll-Help.xml
ms.assetid: 0C7F2329-99BF-4C9E-A307-0C7F7145218F
manager: dansimp
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Remove-ADFSAttributeStore

## SYNOPSIS
Removes an attribute store from the Federation Service.

## SYNTAX

### Name
```
Remove-ADFSAttributeStore [-TargetName] <String> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject
```
Remove-ADFSAttributeStore [-TargetAttributeStore] <AttributeStore> [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The Remove-ADFSAttributeStore cmdlet removes an attribute store from the Federation Service.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
C:\PS>Remove-ADFSAttributeStore -TargetName "My Attribute Store"
```

Description

-----------

Removes an attribute store from the Federation Service.

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

### -PassThru
Passes an object to the pipeline.
By default, this cmdlet does not generate any output.

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

### -TargetAttributeStore
Specifies the attribute store to remove.
This value is typically taken from the pipeline.

```yaml
Type: AttributeStore
Parameter Sets: InputObject
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -TargetName
Specifies the name of the attribute store to remove.

```yaml
Type: String
Parameter Sets: Name
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
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

### Microsoft.IdentityServer.PowerShell.Resources.AttributeStore
A class structure that represents an AD FS 2.0 attribute store object

## OUTPUTS

### None

## NOTES
* An Active Directory Federation Services (AD FS) 2.0 attribute store is a pluggable module that the policy process for AD FS 2.0 can query to retrieve claim values. You can use either an Active Directory database or a Microsoft SQL Server database as your attribute store, or you can create your own custom attribute store.

## RELATED LINKS

[Add-ADFSAttributeStore](./Add-ADFSAttributeStore.md)

[Get-ADFSAttributeStore](./Get-ADFSAttributeStore.md)

[Set-ADFSAttributeStore](./Set-ADFSAttributeStore.md)

