---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: ADFS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/adfs/set-adfsattributestore?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-AdfsAttributeStore
---

# Set-AdfsAttributeStore

## SYNOPSIS
Modifies properties of an attribute store.

## SYNTAX

### Name
```
Set-AdfsAttributeStore [-Name <String>] [-Configuration <Hashtable>] [-TargetName] <String> [-PassThru]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject
```
Set-AdfsAttributeStore [-Name <String>] [-Configuration <Hashtable>] [-TargetAttributeStore] <AttributeStore>
 [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-AdfsAttributeStore** cmdlet modifies properties of an attribute store in the Federation Service.

## EXAMPLES

### Example 1: Modify the configuration of an attribute store
```
PS C:\> Set-AdfsAttributeStore -TargetName "ContosoAttributeStore01" -Configuration @{"runmode" = "verbose"; configParaName2 = configParaValueNew}
```

This command modifies the configuration for the custom attribute store named ContosoAttributeStore01.

## PARAMETERS

### -Configuration
Specifies the initialization parameters of the attribute store, such as a connection string.

```yaml
Type: Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the friendly name of this attribute store.

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
The cmdlet modifies the attribute store that you specify.
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
Specifies the name of the attribute store to modify.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Add-AdfsAttributeStore](./Add-AdfsAttributeStore.md)

[Get-AdfsAttributeStore](./Get-AdfsAttributeStore.md)

[Remove-AdfsAttributeStore](./Remove-AdfsAttributeStore.md)

