---
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
Module Name: ADFS
ms.assetid: 1ACF4732-E32D-4741-8583-79E7BD0D43E6
ms.author: v-anbarr
ms.date: 12/20/2016
ms.mktglfcycl: manage
ms.prod: w10
ms.sitesec: library
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Remove-AdfsAttributeStore
ms.reviewer:
---

# Remove-AdfsAttributeStore

## SYNOPSIS
Removes an attribute store from the Federation Service.

## SYNTAX

### Name
```
Remove-AdfsAttributeStore [-TargetName] <String> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject
```
Remove-AdfsAttributeStore [-TargetAttributeStore] <AttributeStore> [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Remove-AdfsAttributeStore** cmdlet removes an attribute store from the Federation Service.

## EXAMPLES

### Example 1: Remove an attribute store
```
PS C:\> Remove-ADFSAttributeStore -TargetName "ContosoAttributeStore01"
```

This command removes the attribute store named ContosoAttributeStore01 from the Federation Service.

## PARAMETERS

### -PassThru
Returns an object representing the item with which you are working.
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
Specifies an **AttributeStore** object.
The cmdlet removes the **AttributeStore** object that you specify.
To obtain an attribute store, use the **Get-AdfsAttributeStore** cmdlet.

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

### Microsoft.IdentityServer.PowerShell.Resources.AttributeStore
You can pipe a class structure that represents an AD FS 2.0 attribute store object.

## OUTPUTS

## NOTES
* An Active Directory Federation Services (AD FS) 2.0 attribute store is a pluggable module that the policy process for AD FS 2.0 can query to retrieve claim values. You can use either an Active Directory database or a Microsoft SQL Server database as your attribute store, or you can implement your own custom attribute store.

## RELATED LINKS

[Get-AdfsAttributeStore](./Get-AdfsAttributeStore.md)

[Add-AdfsAttributeStore](./Add-AdfsAttributeStore.md)

[Set-AdfsAttributeStore](./Set-AdfsAttributeStore.md)

