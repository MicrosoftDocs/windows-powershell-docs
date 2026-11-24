---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.ActiveDirectory.Management.dll-Help.xml
Module Name: ActiveDirectory
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/activedirectory/set-adobject?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-ADObject
---

# Set-ADObject

## SYNOPSIS
Modifies an Active Directory object.

## SYNTAX

### Identity
```
Set-ADObject [-WhatIf] [-Confirm] [-Add <Hashtable>] [-AuthType <ADAuthType>] [-Clear <String[]>]
 [-Credential <PSCredential>] [-Description <String>] [-DisplayName <String>] [-Identity] <ADObject>
 [-Partition <String>] [-PassThru] [-ProtectedFromAccidentalDeletion <Boolean>] [-Remove <Hashtable>]
 [-Replace <Hashtable>] [-Server <String>] [<CommonParameters>]
```

### Instance
```
Set-ADObject [-WhatIf] [-Confirm] [-AuthType <ADAuthType>] [-Credential <PSCredential>] -Instance <ADObject>
 [-PassThru] [-Server <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-ADObject** cmdlet modifies the properties of an Active Directory object.
You can modify commonly used property values by using the cmdlet parameters.
Property values that are not associated with cmdlet parameters can be modified by using the *Add*, *Replace*, *Clear*, and *Remove* parameters.

The *Identity* parameter specifies the Active Directory object to modify.
You can identify an object by its distinguished name or GUID.
You can also set the *Identity* parameter to an object variable such as `$<localObject>`, or you can pass an object through the pipeline to the *Identity* parameter.
For example, you can use the **Get-ADObject** cmdlet to retrieve an object and then pass the object through the pipeline to the **Set-ADObject** cmdlet.

The *Instance* parameter provides a way to update an object by applying the changes made to a copy of the object.
When you set the *Instance* parameter to a copy of an Active Directory object that has been modified, the **Set-ADObject** cmdlet makes the same changes to the original object.
To get a copy of the object to modify, use the **Get-ADObject** object.
The *Identity* parameter is not allowed when you use the *Instance* parameter.
For more information about the *Instance* parameter, see the *Instance* parameter description.

For Active Directory Lightweight Directory Services (AD LDS) environments, the *Partition* parameter must be specified except in the following two conditions:

- The cmdlet is run from an Active Directory provider drive.
- A default naming context or partition is defined for the AD LDS environment.
To specify a default naming context for an AD LDS environment, set the **msDS-defaultNamingContext** property of the Active Directory directory service agent object (nTDSDSA) for the AD LDS instance.

## EXAMPLES

### Example 1: Set a property on an object by distinguished name
```
PS C:\> Set-ADObject -Identity 'CN=PattiFu Direct Reports,OU=Finance,OU=UserAccounts,DC=FABRIKAM,DC=COM' -Description "Distribution List of Patti Fuller Direct Reports"
```

This command sets the **Description** property on the object with the distinguished name CN=PattiFu Direct Reports,OU=Finance,OU=UserAccounts,DC=FABRIKAM,DC=COM.

### Example 2: Add a site to a property for an object
```
PS C:\> Set-ADObject -Identity 'CN=DEFAULTIPSITELINK,CN=IP,CN=Inter-Site Transports,CN=Sites,CN=Configuration,DC=FABRIKAM,DC=COM' -Add @{siteList='CN=BO3,CN=Sites,CN=Configuration,DC=FABRIKAM,DC=COM'} -Partition 'CN=Configuration,DC=FABRIKAM,DC=COM'
```

This command adds the site CN=BO3,CN=Sites,CN=Configuration,DC=FABRIKAM,DC=COM to the property **siteList** on the object with the distinguished name CN=DEFAULTIPSITELINK,CN=IP,CN=Inter-Site Transports,CN=Sites,CN=Configuration,DC=FABRIKAM,DC=COM.

### Example 3: Add URLs to an object property
```
PS C:\> $UrlValues = @()
PS C:\> $UrlValues += "www.contoso.com"
PS C:\> $UrlValues += "www.fabrikam.com"
PS C:\> Set-ADObject -Identity "cdadd380-d3a8-4fd1-9d30-5cf72d94a056" -Add @{url=$UrlValues}
```

This command adds two new URLs to the **urlValues** property in the object with the GUID cdadd380-d3a8-4fd1-9d30-5cf72d94a056.

### Example 4: Set values for a multi-valued attribute
```
PS C:\> $UrlValues = @()
PS C:\> $UrlValues += "www.contoso.com"
PS C:\> $UrlValues += "www.fabrikam.com"
PS C:\> Set-ADObject -Identity "cdadd380-d3a8-4fd1-9d30-5cf72d94a056" -Replace @{url=$UrlValues;description="Patti Fuller"}
```

This command replaces the old values of the multi-valued attribute **url** with the new values and sets the value of the attribute **description**.

### Example 5: Remove a value from an attribute
```
PS C:\> Set-ADObject -Identity "cdadd380-d3a8-4fd1-9d30-5cf72d94a056" -Remove @{url="www.contoso.com"} -Replace @{description="Patti Fuller (European Manager)"}
```

This command removes the specified value from the **url** attribute and sets the value of the **description** attribute.

### Example 6: Set a UAC bit on an object
```
PS C:\> $MyComp = Get-ADObject -Identity "cdadd380-d3a8-4fd1-9d30-5cf72d94a056" -Properties "userAccountControl","description"
PS C:\> $MyComp.userAccountControl = $MyComp.userAccountControl -bor 50
PS C:\> $MyComp.description = "Setting a new UAC on the object"
PS C:\> Set-ADObject -Instance $MyComp
```

This command sets a new User Access Control (UAC) bit on an object by updating the **userAccountControl** attribute, and sets the value of the **description** attribute.

### Example 7: Protect an object from accidental deletion
```
PS C:\> Set-ADObject -Identity "CN=InternalApps,DC=AppNC" -protectedFromAccidentalDeletion $True -Server "FABRIKAM-SRV1:60000"
```

This command sets container CN=InternalApps,DC=AppNC in an AD LDS instance to be protected from accidental deletion.

### Example 8: Get an object and modify a property
```
PS C:\> Get-ADObject -Identity "SecurityLevel2AccessGroup" | Set-ADObject -DisplayName "Security Level 2"
```

This command modifies the **DisplayName** property for the **SecurityLevel2AccessGroup** object.
The command uses the **Get-ADObject** cmdlet to get the object, and then passes the object to the current cmdlet by using the pipeline operator.

## PARAMETERS

### -Add
Specifies values to add to an object property.
Use this parameter to add one or more values to a property that cannot be modified using a cmdlet parameter.
To modify an object property, you must use the Lightweight Directory Access Protocol (LDAP) display name.
You can specify multiple values to a property by specifying a comma-separated list of values and more than one property by separating them using a semicolon.
The format for this parameter is:

`-Add @{Attribute1LDAPDisplayName=value1, value2, ...;   Attribute2LDAPDisplayName=value1, value2, ...; AttributeNLDAPDisplayName=value1, value2, ...}`

For example, if you want to remove the value 555-222-2222 and add the values 555-222-1111 and 555-222-3333 to Phone-Office-Other attribute (LDAP display name otherTelephone), and add the value 555-222-9999 to Phone-Mobile-Other (LDAP display name otherMobile), set the *Add* and *Remove* parameters as follows:

`-Add @{otherTelephone='555-222-1111', '555-222-3333'; otherMobile='555-222-9999' } -Remove @{otherTelephone='555-222-2222'}`

When you use the *Add*, *Replace*, *Clear*, and *Remove* parameters together, the operations are performed in the following order:

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

For example, if you want to clear the value for the Phone-Office-Other attribute (LDAP display name otherTelephone) set the *Clear* parameter as follows:

`-Clear otherTelephone`

When you use the *Add*, *Replace*, *Clear*, and *Remove* parameters together, the operations are performed in the following order:

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

The following example shows how to set this parameter to a sample description.

`-Description "Description of the object"`

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
Specifies the display name of the object.
This parameter sets the **DisplayName** property of the object.
The LDAP display name (**ldapDisplayName**) for this property is displayName.

The following example shows how to set this parameter:

`-DisplayName "Patti Fuller Laptop"`

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

### -Identity
Specifies an Active Directory object by providing one of the following property values.
The identifier in parentheses is the LDAP display name for the attribute.
The acceptable values for this parameter are:

- Distinguished name
- GUID (objectGUID)

The cmdlet searches the default naming context or partition to find the object.
If two or more objects are found, the cmdlet returns a non-terminating error.

This parameter can also get this object through the pipeline or you can set this parameter to an object instance.

Derived types, such as the following, are also accepted:

- **Microsoft.ActiveDirectory.Management.ADGroup**
- **Microsoft.ActiveDirectory.Management.ADUser**
- **Microsoft.ActiveDirectory.Management.ADComputer**
- **Microsoft.ActiveDirectory.Management.ADServiceAccount**
- **Microsoft.ActiveDirectory.Management.ADFineGrainedPasswordPolicy**
- **Microsoft.ActiveDirectory.Management.ADDomain**

This example shows how to set this parameter to an **ADObject** object instance named ADObjectInstance:

`-Identity $ADObjectInstance`

```yaml
Type: ADObject
Parameter Sets: Identity
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Instance
Specifies a modified copy of an Active Directory object to use to update the actual Active Directory object.
When you specify this parameter, any modifications made to the modified copy of the object are also made to the corresponding Active Directory object.
The cmdlet only updates the object properties that have changed.

The *Instance* parameter can only update Active Directory objects that have been retrieved by using the **Get-ADObject** cmdlet.
When you specify the *Instance* parameter, you cannot specify other parameters that set properties on the object.

The following is an example of how to use the **Get-ADObject** cmdlet to retrieve an instance of the object.
The object is modified by using the PowerShell command line.
Then the **Set-ADObject** cmdlet saves the changes to the Active Directory object.

Step 1: Get a local instance of the object:

`$ObjectInstance = Get-ADObject -Identity  "CN=someObject, DC=contoso,DC=com"`

Step 2: Modify one or more properties of the object instance:

`$ObjectInstance.Description = "New Description"`

Step3: Save your changes to the object:

`Set-ADObject -Instance $ObjectInstance`

```yaml
Type: ADObject
Parameter Sets: Instance
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Partition
Specifies the distinguished name of an Active Directory partition.
The distinguished name must be one of the naming contexts on the current directory server.
The cmdlet searches this partition to find the object defined by the *Identity* parameter.

The following two examples show how to specify a value for this parameter.

`-Partition "CN=Configuration,DC=EUROPE,DC=TEST,DC=CONTOSO,DC=COM"`

`-Partition "CN=Schema,CN=Configuration,DC=EUROPE,DC=TEST,DC=CONTOSO,DC=COM"`

In many cases, a default value is used for the *Partition* parameter if no value is specified.
The rules for determining the default value are given below.
Note that rules listed first are evaluated first and once a default value can be determined, no further rules are evaluated.

In Active Directory Domain Services (AD DS) environments, a default value for *Partition* is set in the following cases:

- If the *Identity* parameter is set to a distinguished name, the default value of *Partition* is automatically generated from this distinguished name.
- If running cmdlets from an Active Directory provider drive, the default value of *Partition* is automatically generated from the current path in the drive.
- If none of the previous cases apply, the default value of *Partition* is set to the default partition or naming context of the target domain.

In AD LDS environments, a default value for *Partition* is set in the following cases:

- If the *Identity* parameter is set to a distinguished name, the default value of *Partition* is automatically generated from this distinguished name.
- If running cmdlets from an Active Directory provider drive, the default value of *Partition* is automatically generated from the current path in the drive.
- If the target AD LDS instance has a default naming context, the default value of *Partition* is set to the default naming context. To specify a default naming context for an AD LDS environment, set the **msDS-defaultNamingContext** property of the Active Directory directory service agent (DSA) object (nTDSDSA) for the AD LDS instance.
- If none of the previous cases apply, the *Partition* parameter does not take any default value.

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

The following example shows how to set this parameter to $True.

`-ProtectedFromAccidentalDeletion $True`

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

For example, if you want to add the values blue and green and remove the value pink from a property with a LDAP display name of FavColors, set the *Add* and *Remove* parameters as follows:

`-Add @{FavColors=Blue,Green} -Remove {FavColors=Pink}`

When you use the *Add*, *Replace*, *Clear*, and *Remove* parameters together, the operations are performed in the following order:

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
You can specify multiple values to a property by specifying a comma-separated list of values, and more than one property by separating them using a semicolon.
The format for this parameter is:

`-Replace @{Attribute1LDAPDisplayName=value1, value2, ...;   Attribute2LDAPDisplayName=value1, value2, ...; AttributeNLDAPDisplayName=value1, value2, ...}`

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
Specifies the AD DS instance to connect to, by providing one of the following values for a corresponding domain name or directory server.
The service may be any of the following: AD LDS, AD DS, or Active Directory snapshot instance.

Domain name values:

- Fully qualified domain name (FQDN)
- NetBIOS name

Directory server values:

- Fully qualified directory server name
- A NetBIOS name
- Fully qualified directory server name and port

The default value for the *Server* parameter is determined by one of the following methods in the order that they are listed:

- By using *Server* value from objects passed through the pipeline.
- By using the server information associated with the Active Directory PowerShell provider drive, when running under that drive.
- By using the domain of the computer running PowerShell.

The following example shows how to specify a FQDN as the parameter value.

`-Server "corp.contoso.com"`

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

### None or Microsoft.ActiveDirectory.Management.ADObject
An Active Directory object is received by the *Identity* parameter.
Derived types, such as the following are also accepted:

- **Microsoft.ActiveDirectory.Management.ADGroup**
- **Microsoft.ActiveDirectory.Management.ADUser**
- **Microsoft.ActiveDirectory.Management.ADComputer**
- **Microsoft.ActiveDirectory.Management.ADServiceAccount**
- **Microsoft.ActiveDirectory.Management.ADOrganizationalUnit**
- **Microsoft.ActiveDirectory.Management.ADFineGrainedPasswordPolicy**
- **Microsoft.ActiveDirectory.Management.ADDomain**

An object that was retrieved by using the **Get-ADObject** cmdlet and then modified is received by the *Instance* parameter.

## OUTPUTS

### None or Microsoft.ActiveDirectory.Management.ADObject
Returns the modified object when the *PassThru* parameter is specified.
By default, this cmdlet does not generate any output.

## NOTES
* This cmdlet does not work with an Active Directory snapshot.
* This cmdlet does not work with a read-only domain controller.

## RELATED LINKS

[Get-ADObject](./Get-ADObject.md)

[Move-ADObject](./Move-ADObject.md)

[New-ADObject](./New-ADObject.md)

[Remove-ADObject](./Remove-ADObject.md)

[Rename-ADObject](./Rename-ADObject.md)

[Restore-ADObject](./Restore-ADObject.md)

