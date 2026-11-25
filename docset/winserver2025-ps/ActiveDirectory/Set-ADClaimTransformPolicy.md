---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.ActiveDirectory.Management.dll-Help.xml
Module Name: ActiveDirectory
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/activedirectory/set-adclaimtransformpolicy?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-ADClaimTransformPolicy
---

# Set-ADClaimTransformPolicy

## SYNOPSIS
Sets the properties of a claims transformation policy in Active Directory.

## SYNTAX

### DenyAllExcept
```
Set-ADClaimTransformPolicy [-WhatIf] [-Confirm] [-Add <Hashtable>] [-AuthType <ADAuthType>] [-Clear <String[]>]
 [-Credential <PSCredential>] -DenyAllExcept <ADClaimType[]> [-Description <String>]
 [-Identity] <ADClaimTransformPolicy> [-PassThru] [-ProtectedFromAccidentalDeletion <Boolean>]
 [-Remove <Hashtable>] [-Replace <Hashtable>] [-Server <String>] [<CommonParameters>]
```

### DenyAll
```
Set-ADClaimTransformPolicy [-WhatIf] [-Confirm] [-Add <Hashtable>] [-AuthType <ADAuthType>] [-Clear <String[]>]
 [-Credential <PSCredential>] [-DenyAll] [-Description <String>] [-Identity] <ADClaimTransformPolicy>
 [-PassThru] [-ProtectedFromAccidentalDeletion <Boolean>] [-Remove <Hashtable>] [-Replace <Hashtable>]
 [-Server <String>] [<CommonParameters>]
```

### Identity
```
Set-ADClaimTransformPolicy [-WhatIf] [-Confirm] [-Add <Hashtable>] [-AuthType <ADAuthType>] [-Clear <String[]>]
 [-Credential <PSCredential>] [-Description <String>] [-Identity] <ADClaimTransformPolicy> [-PassThru]
 [-ProtectedFromAccidentalDeletion <Boolean>] [-Remove <Hashtable>] [-Replace <Hashtable>] [-Rule <String>]
 [-Server <String>] [<CommonParameters>]
```

### AllowAll
```
Set-ADClaimTransformPolicy [-WhatIf] [-Confirm] [-Add <Hashtable>] [-AllowAll] [-AuthType <ADAuthType>]
 [-Clear <String[]>] [-Credential <PSCredential>] [-Description <String>] [-Identity] <ADClaimTransformPolicy>
 [-PassThru] [-ProtectedFromAccidentalDeletion <Boolean>] [-Remove <Hashtable>] [-Replace <Hashtable>]
 [-Server <String>] [<CommonParameters>]
```

### AllowAllExcept
```
Set-ADClaimTransformPolicy [-WhatIf] [-Confirm] [-Add <Hashtable>] -AllowAllExcept <ADClaimType[]>
 [-AuthType <ADAuthType>] [-Clear <String[]>] [-Credential <PSCredential>] [-Description <String>]
 [-Identity] <ADClaimTransformPolicy> [-PassThru] [-ProtectedFromAccidentalDeletion <Boolean>]
 [-Remove <Hashtable>] [-Replace <Hashtable>] [-Server <String>] [<CommonParameters>]
```

### Instance
```
Set-ADClaimTransformPolicy [-WhatIf] [-Confirm] [-AuthType <ADAuthType>] [-Credential <PSCredential>]
 -Instance <ADClaimTransformPolicy> [-PassThru] [-Server <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-ADClaimTransformPolicy** cmdlet can be used to set the properties of a claims transformation policy in Active Directory.
A claims transformation policy object contains a set of rules authored in the transformation rule language.

## EXAMPLES

### Example 1: Set the transformation rule on a specified claims transformation policy
```
PS C:\> Set-ADClaimTransformPolicy -Identity DenyAllPolicy -DenyAll
```

This command sets the transformation rule on the claims transformation policy named DenyAllPolicy to deny all claims, both those that are sent as well as those that are received.

### Example 2: Set the transformation rule on a specified claims transformation policy with exceptions
```
PS C:\> Set-ADClaimTransformPolicy -Identity AllowAllExceptCompanyAndDepartmentPolicy -AllowAllExcept Company,Department
```

This command sets the transformation rule on the claims transformation policy named AllowAllExceptCompanyAndDepartmentPolicy to allow all claims to be sent or received except for the claims Company and Department.

### Example 3: Set the transformation rule on an existing claims transformation policy
```
PS C:\> Set-ADClaimTransformPolicy -Identity HumanResourcesToHrPolicy -Rule 'C1:[Type=="ad://ext/Department:88ce6e1cc00e9524", Value=="Human Resources", ValueType=="string"] => issue(Type=C1.Type, Value="HR", ValueType=C1.ValueType);'
```

This command sets the transformation rule on the claims transformation policy named HumanResourcesToHrPolicy to transform the value Human Resources to HR in the claim ad://ext/Department:88ce6e1cc00e9524.

### Example 4: Set the transformation rule on an claims transformation policy specified in a file
```
PS C:\> $Rule = Get-Content -Path C:\rule.txt
PS C:\> Set-ADClaimTransformPolicy MyRule -Rule $Rule
```

This command sets the transformation rule on the claims transformation policy named MyRule with the rule specified in C:\rule.txt.

## PARAMETERS

### -Add
Specifies values to add to an object property.
Use this parameter to add one or more values to a property that cannot be modified using a cmdlet parameter.
To modify an object property, you must use the Lightweight Directory Access Protocol (LDAP) display name.
You can specify multiple values to a property by specifying a comma-separated list of values and more than one property by separating them using a semicolon.
The format for this parameter is:

`-Add @{Attribute1LDAPDisplayName=value1, value2, ...;   Attribute2LDAPDisplayName=value1, value2, ...; AttributeNLDAPDisplayName=value1, value2, ...}`

When you use the *Add*, *Remove*, *Replace*, and *Clear* parameters together, the operations are performed in the following order:

- **Remove**
- **Add**
- **Replace**
- **Clear**

```yaml
Type: Hashtable
Parameter Sets: DenyAllExcept, DenyAll, Identity, AllowAll, AllowAllExcept
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AllowAll
Indicates whether the policy sets a claims transformation rule that allows all claims to be sent or received.

```yaml
Type: SwitchParameter
Parameter Sets: AllowAll
Aliases:
Accepted values: true

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AllowAllExcept
Specifies an array of claim types.
When this parameter is specified, the policy sets a claims transformation rule that allows all claims to be sent or received except for the specified claim types.

```yaml
Type: ADClaimType[]
Parameter Sets: AllowAllExcept
Aliases:

Required: True
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
Specifies an array of object properties that are cleared in the directory.
Use this parameter to clear one or more values of a property that cannot be modified using a cmdlet parameter.
To modify an object property, you must use the LDAP display name.
You can modify more than one property by specifying a comma-separated list.
The format for this parameter is:

`-Clear Attribute1LDAPDisplayName, Attribute2LDAPDisplayName`

When you use the *Add*, *Remove*, *Replace*, and *Clear* parameters together, the operations are performed in the following order:

- **Remove**
- **Add**
- **Replace**
- **Clear**

```yaml
Type: String[]
Parameter Sets: DenyAllExcept, DenyAll, Identity, AllowAll, AllowAllExcept
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
Specifies a user account that has permission to perform this action.
The default is the current user.

Type a user name, such as User01" or Domain01\User01, or enter a **PSCredential** object, such as one generated by the **Get-Credential** cmdlet.
If you type a user name, you are prompted for a password.

This parameter is not supported by any providers installed with Windows PowerShell.

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

### -DenyAll
Indicates that the policy sets a claims transformation rule that denies all claims to be sent or received.

```yaml
Type: SwitchParameter
Parameter Sets: DenyAll
Aliases:
Accepted values: true

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DenyAllExcept
Specifies an array of claim types.
When this parameter is specified, the claims transformation policy sets a claims transformation rule that denies all claims to be sent or received except for the specified claim types.

```yaml
Type: ADClaimType[]
Parameter Sets: DenyAllExcept
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Description
Specifies a description of the object.
This parameter sets the value of the **Description** property for the object.
The LDAP display name (**ldapDisplayName**) for this property is description.

```yaml
Type: String
Parameter Sets: DenyAllExcept, DenyAll, Identity, AllowAll, AllowAllExcept
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Identity
Specifies one of the following as valid identities for the ADClaimTransformPolicy object:

- A distinguished name
- A GUID (objectGUID)

The cmdlet searches the default naming context or partition to find the object.
If two or more objects are found, the cmdlet returns a non-terminating error.

This parameter can also get this object through the pipeline or you can set this parameter to an object instance.

```yaml
Type: ADClaimTransformPolicy
Parameter Sets: DenyAllExcept, DenyAll, Identity, AllowAll, AllowAllExcept
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Instance
Specifies an instance of an Active Directory object to use as a template for a new claims transformation policy object.

You can use an instance of an existing claims transformation policy object as a template or you can construct a new claims transformation policy object by using the Windows PowerShell command line or by using a script.

Method 1: Use an existing claims transformation policy object as a template for a new object.
To retrieve an instance of an existing claims transformation policy object, use a cmdlet such as **Get-ADClaimTransformPolicy**.
Then provide this object to the Instance parameter of the New-ADClaimTransformPolicy cmdlet to create a new claims transformation policy object.
You can override property values of the new object by setting the appropriate parameters.

Method 2: Create a new **ADClaimTransformPolicy** and set the property values by using the Windows PowerShell command line interface.
Then pass this object to the *Instance* parameter of the **New-ADClaimTransformPolicy** cmdlet to create the new Active Directory object.

Note: Specified attributes are not validated, so attempting to set attributes that do not exist or cannot be set will raise an error.

```yaml
Type: ADClaimTransformPolicy
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
When this property is set to true, you cannot delete the corresponding object without changing the value of the property.
The acceptable values for this parameter are:

- $False or 0
- $True or 1

```yaml
Type: Boolean
Parameter Sets: DenyAllExcept, DenyAll, Identity, AllowAll, AllowAllExcept
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

When you use the *Add*, *Remove*, *Replace*, and *Clear* parameters together, the parameters are applied in the following sequence:

- **Remove**
- **Add**
- **Replace**
- **Clear**

```yaml
Type: Hashtable
Parameter Sets: DenyAllExcept, DenyAll, Identity, AllowAll, AllowAllExcept
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
The format for this parameter is

`-Replace @{Attribute1LDAPDisplayName=value[],   Attribute2LDAPDisplayName=value[]}`

When you use the *Add*, *Remove*, *Replace*, and *Clear* parameters together, the operations are performed in the following order:

- **Remove**
- **Add**
- **Replace**
- **Clear**

```yaml
Type: Hashtable
Parameter Sets: DenyAllExcept, DenyAll, Identity, AllowAll, AllowAllExcept
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Rule
Specifies the claims transformation rule.
To specify the rule, you can either type the rule in a text file, and then pass the file to the cmdlet (recommended), or type the rule inline.

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

### -Server
Specifies the Active Directory Domain Services instance to connect to, by providing one of the following values for a corresponding domain name or directory server.
The service may be any of the following:  Active Directory Lightweight Domain Services, Active Directory Domain Services or Active Directory snapshot instance.

Specify the Active Directory Domain Services instance in one of the following ways:

Domain name values:

- Fully qualified domain name
- NetBIOS name

Directory server values:

- Fully qualified directory server name
- NetBIOS name
- Fully qualified directory server name and port

The default value for this parameter is determined by one of the following methods in the order that they are listed:

- By using the *Server* value from objects passed through the pipeline
- By using the server information associated with the Active Directory Domain Services Windows PowerShell provider drive, when the cmdlet runs in that drive
- By using the domain of the computer running Windows PowerShell

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

### None or Microsoft.ActiveDirectory.Management.ADClaimTransformPolicy
A claim transform policy object is received by the *Identity* parameter.

A claim transform policy object that was retrieved by using the Get-ADClaimTransformPolicy cmdlet and then modified is received by the *Instance* parameter.

## OUTPUTS

### None or Microsoft.ActiveDirectory.Management.ADClaimTransformPolicy
Returns the modified claim transform policy object when the *PassThru* parameter is specified.
By default, this cmdlet does not generate any output.

## NOTES
* This cmdlet does not work with an Active Directory snapshot.
* This cmdlet does not work with a read-only domain controller.

## RELATED LINKS

[Get-ADClaimTransformPolicy](./Get-ADClaimTransformPolicy.md)

[New-ADClaimTransformPolicy](./New-ADClaimTransformPolicy.md)

[Remove-ADClaimTransformPolicy](./Remove-ADClaimTransformPolicy.md)

[AD DS Administration Cmdlets in Windows PowerShell](./activedirectory.md)

