---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.ActiveDirectory.Management.dll-Help.xml
Module Name: ActiveDirectory
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/activedirectory/set-adclaimtype?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-ADClaimType
---

# Set-ADClaimType

## SYNOPSIS
Modify a claim type in Active Directory.

## SYNTAX

### Identity (Default)
```
Set-ADClaimType [-WhatIf] [-Confirm] [-Add <Hashtable>] [-AppliesToClasses <String[]>] [-AuthType <ADAuthType>]
 [-Clear <String[]>] [-Credential <PSCredential>] [-Description <String>] [-DisplayName <String>]
 [-Enabled <Boolean>] [-Identity] <ADClaimType> [-PassThru] [-ProtectedFromAccidentalDeletion <Boolean>]
 [-Remove <Hashtable>] [-Replace <Hashtable>] [-RestrictValues <Boolean>] [-Server <String>]
 [-SuggestedValues <ADSuggestedValueEntry[]>] [<CommonParameters>]
```

### SourceTransformPolicy
```
Set-ADClaimType [-WhatIf] [-Confirm] [-Add <Hashtable>] [-AppliesToClasses <String[]>] [-AuthType <ADAuthType>]
 [-Clear <String[]>] [-Credential <PSCredential>] [-Description <String>] [-DisplayName <String>]
 [-Enabled <Boolean>] [-Identity] <ADClaimType> [-PassThru] [-ProtectedFromAccidentalDeletion <Boolean>]
 [-Remove <Hashtable>] [-Replace <Hashtable>] [-RestrictValues <Boolean>] [-Server <String>]
 [-SourceTransformPolicy] [-SuggestedValues <ADSuggestedValueEntry[]>] [<CommonParameters>]
```

### SourceAttribute
```
Set-ADClaimType [-WhatIf] [-Confirm] [-Add <Hashtable>] [-AppliesToClasses <String[]>] [-AuthType <ADAuthType>]
 [-Clear <String[]>] [-Credential <PSCredential>] [-Description <String>] [-DisplayName <String>]
 [-Enabled <Boolean>] [-Identity] <ADClaimType> [-PassThru] [-ProtectedFromAccidentalDeletion <Boolean>]
 [-Remove <Hashtable>] [-Replace <Hashtable>] [-RestrictValues <Boolean>] [-Server <String>]
 -SourceAttribute <String> [-SuggestedValues <ADSuggestedValueEntry[]>] [<CommonParameters>]
```

### SourceOID
```
Set-ADClaimType [-WhatIf] [-Confirm] [-Add <Hashtable>] [-AppliesToClasses <String[]>] [-AuthType <ADAuthType>]
 [-Clear <String[]>] [-Credential <PSCredential>] [-Description <String>] [-DisplayName <String>]
 [-Enabled <Boolean>] [-Identity] <ADClaimType> [-PassThru] [-ProtectedFromAccidentalDeletion <Boolean>]
 [-Remove <Hashtable>] [-Replace <Hashtable>] [-RestrictValues <Boolean>] [-Server <String>]
 -SourceOID <String> [<CommonParameters>]
```

### Instance
```
Set-ADClaimType [-WhatIf] [-Confirm] [-AuthType <ADAuthType>] [-Credential <PSCredential>]
 -Instance <ADClaimType> [-PassThru] [-Server <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-ADClaimType** cmdlet can be used to modify a claim type in Active Directory.

## EXAMPLES

### Example 1: Set a user claim display name to a source from an Active Directory source
```
PS C:\> Set-ADClaimType -Identity Title -SourceAttribute "title"
```

This command sets the user claim type with display name Title to source from the Active Directory attribute **title**.

### Example 2: Set the suggested values of a user claim
```
PS C:\> $FullTime = New-Object Microsoft.ActiveDirectory.Management.ADSuggestedValueEntry("FTE", "Full-Time", "Full-time employee")
PS C:\> $Intern = New-Object Microsoft.ActiveDirectory.Management.ADSuggestedValueEntry("Intern", "Intern", "Student employee")
PS C:\> $Contractor = New-Object Microsoft.ActiveDirectory.Management.ADSuggestedValueEntry("Contractor", "Contractor", "Contract employee")
PS C:\> Set-ADClaimType -Identity "Employee Type" -SuggestedValues $FullTime,$Intern,$Contractor
```

This command sets the suggested values of the user claim type with display name Employee Type to FTE, Intern, and Contractor.
Applications using this claim type would allow their users to specify one of the suggested values as this claim type's value.

### Example 3: Set the source OID of a claim type and then disable it
```
PS C:\> Set-ADclaimType -Identity "Bitlocker Enabled" -SourceOID "1.3.6.1.4.1.311.67.1.1" -Enabled $False
```

This example sets the source OID of the claim type with display name Bitlocker Enabled to 1.3.6.1.4.1.311.67.1.1, and disables the claim type.

### Example 4: Set a named claim type to source from the claims transformation policy engine
```
PS C:\> Set-ADClaimType -Identity SourceForest -SourceTransformPolicy
```

This command sets the claim type named SourceForest to source from the claims transformation policy engine.

## PARAMETERS

### -Add
Specifies values to add to an object property.
Use this parameter to add one or more values to a property that cannot be modified using a cmdlet parameter.
To modify an object property, you must use the Lightweight Directory Access Protocol (LDAP) display name.
You can specify multiple values to a property by specifying a comma-separated list of values and more than one property by separating them using a semicolon.
The format for this parameter is:

`-Add @{Attribute1LDAPDisplayName=value1, value2, ...;   Attribute2LDAPDisplayName=value1, value2, ...; AttributeNLDAPDisplayName=value1, value2, ...}`

When you use the *Add*, *Replace*, *Clear*, and *Remove* parameters together, the operations are performed in the following order:

- **Remove**
- **Add**
- **Replace**
- **Clear**

```yaml
Type: Hashtable
Parameter Sets: Identity, SourceTransformPolicy, SourceAttribute, SourceOID
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AppliesToClasses
Specifies the names, GUIDs, or distinguished names of the schema classes to which this claim type is applied.

```yaml
Type: String[]
Parameter Sets: Identity, SourceTransformPolicy, SourceAttribute, SourceOID
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
Specifies an array of object properties that are cleared in the directory.
Use this parameter to clear one or more values of a property that cannot be modified using a cmdlet parameter.
To modify an object property, you must use the LDAP display name.
You can modify more than one property by specifying a comma-separated list.
The format for this parameter is:

-Clear Attribute1LDAPDisplayName, Attribute2LDAPDisplayName

When you use the *Add*, *Replace*, *Clear*, and *Remove* parameters together, the operations are performed in the following order:

- **Remove**
- **Add**
- **Replace**
- **Clear**

```yaml
Type: String[]
Parameter Sets: Identity, SourceTransformPolicy, SourceAttribute, SourceOID
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
The default credentials are the credentials of the currently logged on user unless the cmdlet is run from an Active Directory module for Windows PowerShell provider drive.
If the cmdlet is run from such a provider drive, the account associated with the drive is the default.

To specify this parameter, you can type a user name, such as User1 or Domain01\User01 or you can specify a **PSCredential** object.
If you specify a user name for this parameter, the cmdlet prompts for a password.

You can also create a **PSCredential** object by using a script or by using the **Get-Credential** cmdlet.
You can then set the *Credential* parameter to the **PSCredential** object.

If the acting credentials do not have directory-level permission to perform the task, Active Directory module for Windows PowerShell returns a terminating error.

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
The LDAP display name (**ldapDisplayName**) for this property is description.

```yaml
Type: String
Parameter Sets: Identity, SourceTransformPolicy, SourceAttribute, SourceOID
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisplayName
Specifies the display name of the claim type.
The display name of the claim type must be unique.
The display name of a claim type can be used as an identity in other Active Directory cmdlets.

```yaml
Type: String
Parameter Sets: Identity, SourceTransformPolicy, SourceAttribute, SourceOID
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Enabled
Specifies if the claim type is enabled.

```yaml
Type: Boolean
Parameter Sets: Identity, SourceTransformPolicy, SourceAttribute, SourceOID
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
- A security identifier (objectSid)
- A SAM account name (sAMAccountName)

This parameter can also get this object through the pipeline or you can set this parameter to an object instance.

```yaml
Type: ADClaimType
Parameter Sets: Identity, SourceTransformPolicy, SourceAttribute, SourceOID
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Instance
Specifies an instance of a claim type object to use as a template for a new claim type object.

You can use an instance of an existing claim type object as a template or you can construct a new claim type object by using the Windows PowerShell command line or by using a script.

Method 1: Use an existing claim type object as a template for a new object.
To retrieve an instance of an existing claim type object, use a cmdlet such as **Get-ADClaimType**.
Then provide this object to the *Instance* parameter of the **New-ADClaimType** cmdlet to create a new claim type object.
You can override property values of the new object by setting the appropriate parameters.

Method 2: Create a new claim type and set the property values by using the Windows PowerShell command line interface.
Then pass this object to the *Instance* parameter of the New-ADClaimType cmdlet to create the new claim type object.

Note: Specified attributes are not validated, so attempting to set attributes that do not exist or cannot be set will raise an error.

```yaml
Type: ADClaimType
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
Parameter Sets: Identity, SourceTransformPolicy, SourceAttribute, SourceOID
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

When you use the *Add*, *Replace*, *Clear*, and *Remove* parameters together, the parameters are applied in the following sequence:

- **Remove**
- **Add**
- **Replace**
- **Clear**

```yaml
Type: Hashtable
Parameter Sets: Identity, SourceTransformPolicy, SourceAttribute, SourceOID
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

When you use the *Add*, *Replace*, *Clear*, and *Remove* parameters together, the operations are performed in the following order:

- **Remove**
- **Add**
- **Replace**
- **Clear**

```yaml
Type: Hashtable
Parameter Sets: Identity, SourceTransformPolicy, SourceAttribute, SourceOID
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RestrictValues
This parameter is used to specify whether the claim type may have values outside of the *SuggestedValues* parameter.
If this is set to $True, then the claim should only have values specified in the *SuggestedValues* parameter.
Note that Active Directory does not enforce this restriction.
It is up to the applications that use these claims to enforce the restriction.

```yaml
Type: Boolean
Parameter Sets: Identity, SourceTransformPolicy, SourceAttribute, SourceOID
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

### -SourceAttribute
Specifies an Active Directory attribute from which this claim type is based, and from which the claim value is obtained.
The input must be the distinguished name, Name, or GUID of the attribute definition in the schema.

Acceptable values include attributes of the following schema class objects: **User**, **InetOrgPerson**, **Computer**, **ManagedServiceAccount**, **GroupManagedServiceAccount**, and **Auxiliary**, except for the following attributes:

 Attributes marked as defunct in the schema- Blocked attributes such as **dBCSPwd**, **lmPwdHistory**, and **unicodePwd**
 Attributes that are not replicated
 Attributes that are not available on read-only domain controllers
 Attributes with syntaxes not based on the following:

- String Object (DS-DN)
- String (Unicode)
- Boolean
- Integer
- Large Integer
- String (OID)
- String (SD)

```yaml
Type: String
Parameter Sets: SourceAttribute
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SourceOID
Specifies a string to use to configure a certificate-based claim type source.
For example, use this parameter to create certificate-based claim types when you want to use smartcard logon claims for authorization decisions.
This parameter uses the string representation of an object identifier (OID) from the issuance policy found in the certificate and on the certificate template when using Active Directory Certificate Services.
An example of an OID is 1.3.6.1.4.1.311.47.2.5.

```yaml
Type: String
Parameter Sets: SourceOID
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SourceTransformPolicy
Indicates that the claim type is sourced from the claims transformation policy engine.

```yaml
Type: SwitchParameter
Parameter Sets: SourceTransformPolicy
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SuggestedValues
Specifies one or more suggested values for the claim type.
An application may choose to present this list of suggested values for the user to choose from.
When *RestrictValues* is set to $True, the application should restrict the user to pick values from this list only.

```yaml
Type: ADSuggestedValueEntry[]
Parameter Sets: Identity, SourceTransformPolicy, SourceAttribute
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

### None or Microsoft.ActiveDirectory.Management.ADClaimType

## OUTPUTS

### None or Microsoft.ActiveDirectory.Management.ADClaimType

## NOTES
* This cmdlet does not work with an Active Directory snapshot.
* This cmdlet does not work with a read-only domain controller.

## RELATED LINKS

[Get-ADClaimType](./Get-ADClaimType.md)

[New-ADClaimType](./New-ADClaimType.md)

