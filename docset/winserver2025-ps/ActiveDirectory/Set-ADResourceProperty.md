---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.ActiveDirectory.Management.dll-Help.xml
Module Name: ActiveDirectory
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/activedirectory/set-adresourceproperty?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-ADResourceProperty
---

# Set-ADResourceProperty

## SYNOPSIS
Modifies a resource property in Active Directory.

## SYNTAX

### Identity
```
Set-ADResourceProperty [-WhatIf] [-Confirm] [-Add <Hashtable>] [-AppliesToResourceTypes <Hashtable>]
 [-AuthType <ADAuthType>] [-Clear <String[]>] [-Credential <PSCredential>] [-Description <String>]
 [-DisplayName <String>] [-Enabled <Boolean>] [-Identity] <ADResourceProperty> [-PassThru]
 [-ProtectedFromAccidentalDeletion <Boolean>] [-Remove <Hashtable>] [-Replace <Hashtable>] [-Server <String>]
 [-SharesValuesWith <ADClaimType>] [-SuggestedValues <ADSuggestedValueEntry[]>] [<CommonParameters>]
```

### Instance
```
Set-ADResourceProperty [-WhatIf] [-Confirm] [-AuthType <ADAuthType>] [-Credential <PSCredential>]
 -Instance <ADResourceProperty> [-PassThru] [-Server <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-ADResourceProperty** cmdlet can be used to modify a resource property in Active Directory.

## EXAMPLES

### Example 1: Set the suggested values for a resource property
```
PS C:\> $US = New-Object Microsoft.ActiveDirectory.Management.ADSuggestedValueEntry("US", "United States of America", "United States of America")
PS C:\> $JP = New-Object Microsoft.ActiveDirectory.Management.ADSuggestedValueEntry("JP", "Japan", "Japan")
PS C:\> Set-ADResourceProperty -Identity Country -SuggestedValues $US,$JP
```

This command sets the suggested values of the resource property with display name Country to US and JP.
Applications using this resource property would allow their users to specify one of the suggested values as this resource property's value.

### Example 2: Set a reference property to use shared values
```
PS C:\> Set-ADResourceProperty -Identity Country -SharesValuesWith Country
```

This command sets the resource property with display name Country to reference an existing claim type named **Country** for its suggested values.
This enables the resource property to be always valid for comparisons with the referenced claim type in a central access rule.

## PARAMETERS

### -Add
Specifies values to add to an object property.
Use this parameter to add one or more values to a property that cannot be modified using a cmdlet parameter.
To modify an object property, you must use the Lightweight Directory Access Protocol (LDAP) display name.
You can specify multiple values to a property by specifying a comma-separated list of values and more than one property by separating them using a semicolon.
The format for this parameter is:

`-Add @{Attribute1LDAPDisplayName=value1, value2, ...;   Attribute2LDAPDisplayName=value1, value2, ...; AttributeNLDAPDisplayName=value1, value2, ...}`

When you use the *Add*, *Remove*, *Replace*, and *Clear*  parameters together, the operations will be performed in the following order:

- **Remove**
- **Add**
- **Replace**
- **Clear**

```yaml
Type: Hashtable
Parameter Sets: Identity
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AppliesToResourceTypes
Specifies the list of resource types that this property applies to.
For Set-ADResourceProperty operations, you can add or include new resource types within an existing property by specifying them using this parameter.
You do not have to specify all previously listed resource types already within this property.

```yaml
Type: Hashtable
Parameter Sets: Identity
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AuthType
Specifies the authentication method to use.
The acceptable values for this parameter are:

- Negotiate or 0
- Basic or 1

The default authentication method is Negotiate.

A Secure Sockets Layer (SSL) connection is required for the Basic authentication method.

```yaml
Type: ADAuthType
Parameter Sets: (All)
Aliases:
Accepted values: Negotiate, Basic

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Clear
Specifies an array of object properties that will be cleared in the directory.
Use this parameter to clear one or more values of a property that cannot be modified using a cmdlet parameter.
To modify an object property, you must use the LDAP display name.
You can modify more than one property by specifying a comma-separated list.
The format for this parameter is:

`-Clear Attribute1LDAPDisplayName, Attribute2LDAPDisplayName`

When you use the *Add*, *Remove*, *Replace*, and *Clear* parameters together, the operations will be performed in the following order:

- **Remove**
- **Add**
- **Replace**
- **Clear**

```yaml
Type: String[]
Parameter Sets: Identity
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

### -Credential
Specifies the user account credentials to use to perform this task.
The default credentials are the credentials of the currently logged on user unless the cmdlet is run from an Active Directory PowerShell provider drive.
If the cmdlet is run from such a provider drive, the account associated with the drive is the default.

To specify this parameter, you can type a user name, such as User1 or Domain01\User01 or you can specify a **PSCredential** object.
If you specify a user name for this parameter, the cmdlet prompts for a password.

You can also create a **PSCredential** object by using a script or by using the **Get-Credential** cmdlet.
You can then set the *Credential* parameter to the **PSCredential** object.

If the acting credentials do not have directory-level permission to perform the task, Active Directory PowerShell returns a terminating error.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Description
Specifies a description of the object.
This parameter sets the value of the **Description** property for the object.
The LDAP Display Name (**ldapDisplayName**) for this property is description.

```yaml
Type: String
Parameter Sets: Identity
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisplayName
Displays the name of the resource property.
The display name of the resource property must be unique.

```yaml
Type: String
Parameter Sets: Identity
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Enabled
Specifies whether the resource property is enabled.

```yaml
Type: Boolean
Parameter Sets: Identity
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Identity
Specifies an Active Directory object by providing one of the following property values.
The identifier in parentheses is the LDAP display name for the attribute.
The acceptable values for this parameter are:

- A distinguished name
- A GUID (objectGUID)

This parameter can also get this object through the pipeline or you can set this parameter to an object instance.

```yaml
Type: ADResourceProperty
Parameter Sets: Identity
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Instance
Specifies an instance of a resource property object to use as a template for a new resource property object.

You can use an instance of an existing resource property object as a template or you can construct a new resource property object by using the Windows PowerShell command line or by using a script.

Method 1: Use an existing resource property object as a template for a new object.
To retrieve an instance of an existing resource property object, use a cmdlet such as **Get-ADResourceProperty**.
Then provide this object to the *Instance* parameter of the **New-ADResourceProperty** cmdlet to create a new resource property object.
You can override property values of the new object by setting the appropriate parameters.

Method 2: Create a new **ADResourceProperty** and set the property values by using the Windows PowerShell command line interface.
Then pass this object to the *Instance* parameter of the **New-ADResourceProperty** cmdlet to create the new resource property object.

Note: Specified attributes are not validated, so attempting to set attributes that do not exist or cannot be set raises an error.

```yaml
Type: ADResourceProperty
Parameter Sets: Instance
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

### -ProtectedFromAccidentalDeletion
Specifies whether to prevent the object from being deleted.
When this property is set to $True, you cannot delete the corresponding object without changing the value of the property.
The acceptable values for this parameter are:

- $False or 0
- $True or 1

```yaml
Type: Boolean
Parameter Sets: Identity
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Remove
Specifies that the cmdlet remove values of an object property.
Use this parameter to remove one or more values of a property that cannot be modified using a cmdlet parameter.
To remove an object property, you must use the LDAP display name.
You can remove more than one property by specifying a semicolon-separated list.
The format for this parameter is:

`-Remove @{Attribute1LDAPDisplayName=value[];   Attribute2LDAPDisplayName=value[]}`

When you use the *Add*, *Remove*, *Replace*, and *Clear* parameters together, the operations will be performed in the following order:

- **Remove**
- **Add**
- **Replace**
- **Clear**

```yaml
Type: Hashtable
Parameter Sets: Identity
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Replace
Specifies values for an object property that will replace the current values.
Use this parameter to replace one or more values of a property that cannot be modified using a cmdlet parameter.
To modify an object property, you must use the LDAP display name.
You can modify more than one property by specifying a comma-separated list.
The format for this parameter is:

`-Replace @{Attribute1LDAPDisplayName=value[],   Attribute2LDAPDisplayName=value[]}`

When you use the *Add*, *Remove*, *Replace*, and *Clear* parameters together, the operations will be performed in the following order:

- **Remove**
- **Add**
- **Replace**
- **Clear**

```yaml
Type: Hashtable
Parameter Sets: Identity
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Server
`-Add @{Attribute1LDAPDisplayName=value1, value2, ...;   Attribute2LDAPDisplayName=value1, value2, ...; AttributeNLDAPDisplayName=value1, value2, ...}`

When you use the *Add*, *Remove*, *Replace*, and *Clear* parameters together, the operations will be performed in the following order:

- **Remove**
- **Add**
- **Replace**
- **Clear**

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

### -SharesValuesWith
Specifies a reference resource property.
Reference resource properties do not provide their own suggested values, but rather use the suggested values from the claim type object specified in this parameter.
This enables the resource property to be always valid for comparisons with the referred claim type in a central access rule.

```yaml
Type: ADClaimType
Parameter Sets: Identity
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SuggestedValues
Specifies one or more suggested values for the resource property.
An application may choose to present this list of suggested values for the user to choose from.
When **RestrictValues** is set to $True, the application should restrict the user to pick values from this list only.

```yaml
Type: ADSuggestedValueEntry[]
Parameter Sets: Identity
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

### None or Microsoft.ActiveDirectory.Management.ADResourceProperty

## OUTPUTS

### None or Microsoft.ActiveDirectory.Management.ADResourceProperty

## NOTES
* This cmdlet does not work with an Active Directory snapshot.
* This cmdlet does not work with a read-only domain controller.

## RELATED LINKS

[Get-ADResourceProperty](./Get-ADResourceProperty.md)

[New-ADResourceProperty](./New-ADResourceProperty.md)

[Remove-ADResourceProperty](./Remove-ADResourceProperty.md)

