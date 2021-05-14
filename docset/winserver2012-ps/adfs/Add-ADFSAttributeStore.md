---
external help file: Microsoft.IdentityServer.PowerShell.dll-Help.xml
Module Name: ADFS
online version: https://docs.microsoft.com/powershell/module/adfs/add-adfsattributestore?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Add-ADFSAttributeStore

## SYNOPSIS
Adds an attribute store to the Federation Service.

## SYNTAX

### Predefined
```
Add-ADFSAttributeStore -Name <String> -StoreType <String> -Configuration <Hashtable> [-PassThru] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### Custom
```
Add-ADFSAttributeStore -Name <String> -TypeQualifiedName <String> -Configuration <Hashtable> [-PassThru]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The Add-ADFSAttributeStore cmdlet adds an attribute store to the Federation Service.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
C:\PS>Add-ADFSAttributeStore -name 'LocalSqlStore' -StoreType 'SQL' -Configuration @{"name" = "SQL Attribute Store"; "Connection" = "Server=CONTOSOSRV01;Database=UserAttributes;Integrated Security=True;Async=True"}
```

Description

-----------

Adds a SQL-based attribute store named LocalSqlStore.

### -------------------------- EXAMPLE 2 --------------------------
```
C:\PS>Add-ADFSAttributeStore -Name 'MyCustomStore' -TypeQualifiedName 'Contoso.CustomTypes.MyAttributeStore, Contoso.CustomTypes' -Configuration @{"Name" = "Custom Attribute Store"; "Connection" = "Default"}
```

Description

-----------

Adds a custom attribute store named MyCustomStore.

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

### -StoreType
Specifies the type of attribute store to add. 
Valid values are ActiveDirectory, LDAP, and SQL.

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
Specifies the class reference for a custom attribute store that is implemented in a .NET Assembly.

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

## OUTPUTS

### None

## NOTES
* An Active Directory Federation Services (AD FS) 2.0 attribute store is a pluggable module that the policy process for AD FS 2.0 can query to retrieve claim values. You can use either an Active Directory database or a Microsoft SQL Server database as your attribute store, or you can implement your own custom attribute store.

## RELATED LINKS

[Get-ADFSAttributeStore](./Get-ADFSAttributeStore.md)

[Remove-ADFSAttributeStore](./Remove-ADFSAttributeStore.md)

[Set-ADFSAttributeStore](./Set-ADFSAttributeStore.md)

