---
external help file: Microsoft.ActiveDirectory.Management.dll-Help.xml
Module Name: ActiveDirectory
online version: https://learn.microsoft.com/powershell/module/activedirectory/set-adorganizationalunit?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-ADOrganizationalUnit

## SYNOPSIS
Modifies an Active Directory organizational unit.

## SYNTAX

### Identity
```
Set-ADOrganizationalUnit [-WhatIf] [-Confirm] [-Add <Hashtable>] [-AuthType <ADAuthType>] [-City <String>]
 [-Clear <String[]>] [-Country <String>] [-Credential <PSCredential>] [-Description <String>]
 [-DisplayName <String>] [-Identity] <ADOrganizationalUnit> [-ManagedBy <ADPrincipal>] [-Partition <String>]
 [-PassThru] [-PostalCode <String>] [-ProtectedFromAccidentalDeletion <Boolean>] [-Remove <Hashtable>]
 [-Replace <Hashtable>] [-Server <String>] [-State <String>] [-StreetAddress <String>] [<CommonParameters>]
```

### Instance
```
Set-ADOrganizationalUnit [-WhatIf] [-Confirm] [-AuthType <ADAuthType>] [-Credential <PSCredential>]
 -Instance <ADOrganizationalUnit> [-PassThru] [-Server <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-ADOrganizationalUnit** cmdlet modifies the properties of an Active Directory organizational unit (OU).
You can modify commonly used property values by using the cmdlet parameters.
**Property** values that are not associated with cmdlet parameters can be modified by using the *Add*, *Remove*, *Replace*, and *Clear* parameters.

The *Identity* parameter specifies the Active Directory organizational unit to modify.
You can identify an organizational unit by its distinguished name or GUID.

You can also set the *Identity* parameter to an object variable such as `$<localADOrganizationalUnitObject>`, or you can pass an object through the pipeline to the *Identity* parameter.
For example, you can use the **Get-ADOrganizationalUnit** cmdlet to retrieve an organizational unit object and then pass the object through the pipeline to the **Set-ADOrganizationalUnit** cmdlet.

The *Instance* parameter provides a way to update an organizational unit object by applying the changes made to a copy of the object.
When you set the *Instance* parameter to a copy of an Active Directory organizational unit object that has been modified, the **Set-ADOrganizationalUnit** cmdlet makes the same changes to the original organizational unit object.
To get a copy of the object to modify, use the **Get-ADOrganizationalUnit** object.
When you specify the *Instance* parameter you should not pass the *Identity* parameter.
For more information about the *Instance* parameter, see the *Instance* parameter description.

For Active Directory Lightweight Directory Services (AD LDS) environments, the *Partition* parameter must be specified except in the following two conditions:

- The cmdlet is run from an Active Directory provider drive. 
- A default naming context or partition is defined for the AD LDS environment.
To specify a default naming context for an AD LDS environment, set the **msDS-defaultNamingContext** property of the Active Directory directory service agent object (**nTDSDSA**) for the AD LDS instance.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
C:\PS>Set-ADOrganizationalUnit -Identity "OU=UserAccounts,DC=FABRIKAM,DC=COM" -Description "This Organizational Unit holds all of the users accounts of FABRIKAM.COM"
```

Description

-----------

Sets the description of the OrganizationalUnit with distinguishedName OU=UserAccounts,DC=FABRIKAM,DC=COM.

### -------------------------- EXAMPLE 2 --------------------------
```
C:\PS>Set-ADOrganizationalUnit -Identity "OU=UserAccounts,DC=FABRIKAM,DC=COM" -ProtectedFromAccidentalDeletion $false
```

Description

-----------

Sets the ProtectedFromAccidentalDeletion property to $false on the OrganizationalUnit with distinguishedName OU=UserAccounts,DC=FABRIKAM,DC=COM.

### -------------------------- EXAMPLE 3 --------------------------
```
C:\PS>Set-ADOrganizationalUnit -Identity "OU=AsiaPacific,OU=Sales,OU=UserAccounts,DC=FABRIKAM,DC=COM" -Country "AU" -StreetAddress "45 Martens Place" -City Balmoral -State QLD -PostalCode 4171 -Replace @{co="Australia"}
```

Description

-----------

Sets the Country, City and State, PostalCode and co properties on the OrganizationalUnit 'OU=AsiaPacific,OU=Sales,OU=UserAccounts,DC=FABRIKAM,DC=COM'.

### -------------------------- EXAMPLE 4 --------------------------
```
C:\PS>$EuropeSalesOU = Get-ADOrganizationalUnit "OU=Europe,OU=Sales,OU=UserAccounts,DC=FABRIKAM,DC=COM"
$EuropeSalesOU.Country = "UK"
$EuropeSalesOU.StreetAddress = "22 Station Rd"
$EuropeSalesOU.City = "QUARRINGTON"
$EuropeSalesOU.PostalCode = "NG34 0NI"
$EuropeSalesOU.co ="United Kingdom"
Set-ADOrganizationalUnit -Instance $EuropeSalesOU
```

Description

-----------

Creates a new OrganizationalUnit using the OrganizationalUnit 'OU=Europe,OU=Sales,OU=UserAccounts,DC=FABRIKAM,DC=COM' as a template.

### -------------------------- EXAMPLE 5 --------------------------
```
C:\PS>Set-ADOrganizationalUnit -Identity "OU=Managed,DC=AppNC" -Server "FABRIKAM-SRV1:60000" -Country "UK"
```

Description

-----------

Set the Country property of the OrganizationalUnit 'OU=Managed,DC=AppNC' in an AD LDS instance.

## PARAMETERS

### -Add
Specifies values to add to an object property.
Use this parameter to add one or more values to a property that cannot be modified using a cmdlet parameter.
To modify an object property, you must use the LDAP display name.
You can specify multiple values to a property by specifying a comma-separated list of values and more than one property by separating them using a semicolon..
The format for this parameter is

-Add @{Attribute1LDAPDisplayName=value1, value2, ...;   Attribute2LDAPDisplayName=value1, value2, ...; AttributeNLDAPDisplayName=value1, value2, ...}

For example, if you want to remove the value "555-222-2222" and add the values "555-222-1111" and "555-222-3333" to Phone-Office-Other attribute (LDAP display name 'otherTelephone'), and add the value "555-222-9999" to Phone-Mobile-Other (LDAP display name 'otherMobile'), set the Add and Remove parameters as follows.

-Add @{otherTelephone='555-222-1111', '555-222-3333'; otherMobile='555-222-9999' } -Remove @{otherTelephone='555-222-2222'}

When you use the Add, Remove, Replace and Clear parameters together, the operations will be performed in the following order:

..Remove

..Add

..Replace

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
Possible values for this parameter include:

Negotiate or 0

Basic or 1

The default authentication method is Negotiate.

A Secure Sockets Layer (SSL) connection is required for the Basic authentication method.

The following example shows how to set this parameter to Basic.

-AuthType Basic

```yaml
Type: ADAuthType
Parameter Sets: (All)
Aliases: 
Accepted values: Negotiate, Basic

Required: False
Position: Named
Default value: Microsoft.ActiveDirectory.Management.AuthType.Negotiate
Accept pipeline input: False
Accept wildcard characters: False
```

### -City
Specifies the user's town or city.
This parameter sets the City property of a user.
The LDAP display name (ldapDisplayName) of this property is "l".

The following example shows how set this parameter.

-City "Las Vegas"

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

### -Clear
Specifies an array of object properties that will be cleared in the directory.
Use this parameter to clear one or more values of a property that cannot be modified using a cmdlet parameter.
To modify an object property, you must use the LDAP display name.
You can modify more than one property by specifying a comma-separated list.
The format for this parameter is

-Clear Attribute1LDAPDisplayName, Attribute2LDAPDisplayName

For example, if you want to clear the value for the Phone-Office-Other attribute (LDAP display name 'otherTelephone') set the Clear parameter as follows.

-Clear otherTelephone

When you use the Add, Remove, Replace and Clear parameters together, the operations will be performed in the following order:

..Remove

..Add

..Replace

..Clear

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

### -Country
Specifies the country or region code for the user's language of choice.
This parameter sets the Country property of a user object.
The LDAP Display Name (ldapDisplayName) of this property is "c".
This value is not used by Windows 2000.

The following example shows how set this parameter.

-Country "IN"

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

### -Credential
Specifies the user account credentials to use to perform this task.
The default credentials are the credentials of the currently logged on user unless the cmdlet is run from an Active Directory PowerShell provider drive.
If the cmdlet is run from such a provider drive, the account associated with the drive is the default.

To specify this parameter, you can type a user name, such as "User1" or "Domain01\User01" or you can specify a PSCredential object.
If you specify a user name for this parameter, the cmdlet prompts for a password.

You can also create a PSCredential object by using a script or by using the Get-Credential cmdlet.
You can then set the Credential parameter to the PSCredential object The following example shows how to create credentials.

$AdminCredentials = Get-Credential "Domain01\User01"

The following shows how to set the Credential parameter to these credentials.

-Credential $AdminCredentials

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
This parameter sets the value of the Description property for the object.
The LDAP Display Name (ldapDisplayName) for this property is "description".

The following example shows how to set this parameter to a sample description.

-Description "Description of the object"

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
This parameter sets the DisplayName property of the object.
The LDAP Display Name (ldapDisplayName) for this property is "displayName".

The following example shows how to set this parameter.

-DisplayName "Sara Davis Laptop"

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

Distinguished Name

Example: CN=saradavis,OU=users,OU=asia,DC=corp,DC=contoso,DC=com

GUID (objectGUID)

Example: 599c3d2e-f72d-4d20-8a88-030d99495f20

The cmdlet searches the default naming context or partition to find the object.
If two or more objects are found, the cmdlet returns a non-terminating error.

This parameter can also get this object through the pipeline or you can set this parameter to an object instance.

Derived types, such as the following are also accepted:

Microsoft.ActiveDirectory.Management.ADGroup

Microsoft.ActiveDirectory.Management.ADUser

Microsoft.ActiveDirectory.Management.ADComputer

Microsoft.ActiveDirectory.Management.ADServiceAccount

Microsoft.ActiveDirectory.Management.ADFineGrainedPasswordPolicy

Microsoft.ActiveDirectory.Management.ADDomain

This example shows how to set this parameter to an ADObject object instance named "ADObjectInstance".

-Identity   $ADObjectInstance

```yaml
Type: ADOrganizationalUnit
Parameter Sets: Identity
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Instance
Specifies a modified copy of an organizational unit object to use to update the actual Active Directory organizational unit object.
When this parameter is used, any modifications made to the modified copy of the object are also made to the corresponding Active Directory object.
The cmdlet only updates the object properties that have changed.

The Instance parameter can only update organizational unit objects that have been retrieved by using the Get-ADOrganizationalUnit cmdlet.
When you specify the Instance parameter, you cannot specify other parameters that set properties on the object.

The following is an example of how to use the Get-ADOrganizationalUnit cmdlet to retrieve an instance of the ADOrganizationalUnit object.
The object is modified by using the Windows PowerShell command line.
Then the Set-ADOrganizationalUnit cmdlet saves the changes to the Active Directory object.

Step 1: Retrieve a local instance of the object.

$organizationalUnitInstance = Get-ADOrganizationalUnit  -Identity "OU=Accounting,DC=corp,DC=contoso,DC=com"

Step 2: Modify one or more properties of the object instance.

$organizationalUnitInstance.ManagedBy = "CN=SaraDavisGroup,CN=Europe,CN=Users,DC=corp,DC=contoso,DC=com"

Step3: Save your changes to Accounting.

Set-ADOrganizationalUnit -Instance $organizationalUnitInstance

```yaml
Type: ADOrganizationalUnit
Parameter Sets: Instance
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ManagedBy
Specifies the user or group that manages the object by providing one of the following property values.
Note: The identifier in parentheses is the LDAP display name for the property.

Distinguished Name

Example:  CN=SaraDavis,OU=Europe,CN=Users,DC=corp,DC=contoso,DC=com

GUID (objectGUID)

Example: 599c3d2e-f72d-4d20-8a88-030d99495f20

Security Identifier (objectSid)

Example: S-1-5-21-3165297888-301567370-576410423-1103

SAM Account Name (sAMAccountName)

Example: saradavis

This parameter sets the Active Directory attribute with an LDAP Display Name of "managedBy".

The following example shows how to specify this parameter.

-ManagedBy ContosoAdmins

```yaml
Type: ADPrincipal
Parameter Sets: Identity
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Partition
Specifies the distinguished name of an Active Directory partition.
The distinguished name must be one of the naming contexts on the current directory server.
The cmdlet searches this partition to find the object defined by the Identity parameter.

The following two examples show how to specify a value for this parameter.

-Partition "CN=Configuration,DC=EUROPE,DC=TEST,DC=CONTOSO,DC=COM"

-Partition "CN=Schema,CN=Configuration,DC=EUROPE,DC=TEST,DC=CONTOSO,DC=COM"

In many cases, a default value will be used for the Partition parameter if no value is specified. 
The rules for determining the default value are given below. 
Note that rules listed first are evaluated first and once a default value can be determined, no further rules will be evaluated.

In AD DS environments, a default value for Partition will be set in the following cases:  - If the Identity parameter is set to a distinguished name, the default value of Partition is automatically generated from this distinguished name.

- If running cmdlets from an Active Directory provider drive, the default value of Partition is automatically generated from the current path in the drive.
- If none of the previous cases apply, the default value of Partition will be set to the default partition or naming context of the target domain.

In AD LDS environments, a default value for Partition will be set in the following cases:

- If the Identity parameter is set to a distinguished name, the default value of Partition is automatically generated from this distinguished name.
- If running cmdlets from an Active Directory provider drive, the default value of Partition is automatically generated from the current path in the drive.
- If the target AD LDS instance has a default naming context, the default value of Partition will be set to the default naming context.  To specify a default naming context for an AD LDS environment, set the msDS-defaultNamingContext property of the Active Directory directory service agent (DSA) object (nTDSDSA) for the AD LDS instance.
- If none of the previous cases apply, the Partition parameter will not take any default value.

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
Returns the new or modified object.
By default (i.e.
if -PassThru is not specified), this cmdlet does not generate any output.

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

### -PostalCode
Specifies the user's postal code or zip code.
This parameter sets the PostalCode property of a user.
The LDAP Display Name (ldapDisplayName) of this property is "postalCode".

The following example shows how to set this parameter.

-PostalCode "28712"

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

### -ProtectedFromAccidentalDeletion
Specifies whether to prevent the object from being deleted.
When this property is set to true, you cannot delete the corresponding object without changing the value of the property.
Possible values for this parameter include:

$false or 0

$true or 1

The following example shows how to set this parameter to true.

-ProtectedFromAccidentalDeletion $true

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
The format for this parameter is

-Remove @{Attribute1LDAPDisplayName=value\[\];   Attribute2LDAPDisplayName=value\[\]}

For example, if you want to add the values blue and green and remove the value pink from a property with a LDAP display name of FavColors, set the Add and Remove parameters as follows.

-Add @{FavColors=Blue,Green} -Remove {FavColors=Pink}

When you use the Add, Remove, Replace and Clear parameters together, the parameters will be applied in the following sequence:

..Remove

..Add

..Replace

..Clear

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
Specifies the Active Directory Domain Services instance to connect to, by providing one of the following values for a corresponding domain name or directory server.
The service may be any of the following:  Active Directory Lightweight Domain Services, Active Directory Domain Services or Active Directory Snapshot instance.

Domain name values:

Fully qualified domain name

Examples: corp.contoso.com

NetBIOS name

Example: CORP

Directory server values:

Fully qualified directory server name

Example: corp-DC12.corp.contoso.com

NetBIOS name

Example: corp-DC12

Fully qualified directory server name and port

Example: corp-DC12.corp.contoso.com:3268

The default value for the Server parameter is determined by one of the following methods in the order that they are listed:

-By using Server value from objects passed through the pipeline.

-By using the server information associated with the Active Directory PowerShell provider drive, when running under that drive.

-By using the domain of the computer running Powershell.

The following example shows how to specify a full qualified domain name as the parameter value.

-Server "corp.contoso.com"

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

### -State
Specifies the user's or Organizational Unit's state or province.
This parameter sets the State property of a User or Organizational Unit object.
The LDAP display name (ldapDisplayName) of this property is "st".

The following example shows how set this parameter.

-State  "Nevada"

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

### -StreetAddress
Specifies the organizational unit's street address.
This parameter sets the StreetAddress property of a organizational unit object.
The LDAP display name (ldapDisplayName) of this property is "street".

The following example shows how to set this parameter.

-StreetAddress  "1200 Main Street"

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

### None or Microsoft.ActiveDirectory.Management.ADOrganizationalUnit
An organizational unit object is received by the Identity parameter.

An organizational unit object that was retrieved by using the Get-ADOrganizationalUnit cmdlet and then modified is received by the Instance parameter.

## OUTPUTS

### None or Microsoft.ActiveDirectory.Management.ADOrganizationalUnit
Returns the modified organizational unit object when the PassThru parameter is specified.
By default, this cmdlet does not generate any output.

## NOTES
* This cmdlet does not work with an Active Directory Snapshot.

  This cmdlet does not work with a read-only domain controller.

## RELATED LINKS

[Get-ADOrganizationalUnit](./Get-ADOrganizationalUnit.md)

[New-ADOrganizationalUnit](./New-ADOrganizationalUnit.md)

[Remove-ADOrganizationalUnit](./Remove-ADOrganizationalUnit.md)

