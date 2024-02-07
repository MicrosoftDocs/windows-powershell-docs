---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: ADFS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/adfs/add-adfsattributestore?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-AdfsAttributeStore
---

# Add-AdfsAttributeStore

## SYNOPSIS
Adds an attribute store to the Federation Service.

## SYNTAX

### Predefined
```
Add-AdfsAttributeStore -Name <String> -StoreType <String> -Configuration <Hashtable> [-PassThru] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### Custom
```
Add-AdfsAttributeStore -Name <String> -TypeQualifiedName <String> -Configuration <Hashtable> [-PassThru]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Add-AdfsAttributeStore** cmdlet adds an attribute store to the Federation Service.

## EXAMPLES

### Example 1: Add a SQL type attribute store
```
PS C:\> Add-AdfsAttributeStore -Name "LocalSqlStore" -StoreType "SQL" -Configuration @{"name" = "SQL Attribute Store"; "Connection" = "Server=CONTOSOSRV01;Database=UserAttributes;Integrated Security=True;Async=True"}
```

This command adds a SQL-based attribute store named LocalSqlStore.

### Example 2: Add a custom attribute store
```
PS C:\> Add-AdfsAttributeStore -Name "MyCustomStore" -TypeQualifiedName "Contoso.CustomTypes.MyAttributeStore, Contoso.CustomTypes" -Configuration @{"Name" = "Custom Attribute Store"; "Connection" = "Default"}
```

This command adds a custom attribute store named MyCustomStore.

## PARAMETERS

### -Configuration
Specifies the initialization parameters of the attribute store, such as a connection string.

```yaml
Type: Hashtable
Parameter Sets: (All)
Aliases:

Required: True
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

Required: True
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

### -StoreType
Specifies the type of attribute store to add.
The acceptable values for this parameter are:

- ActiveDirectory
- LDAP
- SQL

```yaml
Type: String
Parameter Sets: Predefined
Aliases:
Accepted values: ActiveDirectory, LDAP, SQL

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TypeQualifiedName
Specifies the class reference for a custom attribute store that is implemented in a .NET assembly.

```yaml
Type: String
Parameter Sets: Custom
Aliases:

Required: True
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### None or Microsoft.IdentityServer.Management.Resources.AttributeStore

Returns the new AttributeStore object when the *PassThru* parameter is specified. By default, this cmdlet does not generate any output.

## NOTES
* An Active Directory Federation Services (AD FS) 2.0 attribute store is a pluggable module that the policy process for AD FS 2.0 can query to retrieve claim values. You can use either an Active Directory database or a Microsoft SQL Server database as your attribute store, or you can implement your own custom attribute store.

## RELATED LINKS

[Get-AdfsAttributeStore](./Get-AdfsAttributeStore.md)

[Set-AdfsAttributeStore](./Set-AdfsAttributeStore.md)

[Remove-AdfsAttributeStore](./Remove-AdfsAttributeStore.md)

