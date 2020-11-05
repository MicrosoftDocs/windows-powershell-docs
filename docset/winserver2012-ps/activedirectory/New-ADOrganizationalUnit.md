---
external help file: Microsoft.ActiveDirectory.Management.dll-Help.xml
ms.assetid: 41ADB68B-9ADD-45F7-8170-2245BF48DB7B
manager: dansimp
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# New-ADOrganizationalUnit

## SYNOPSIS
Creates a new Active Directory organizational unit.

## SYNTAX

```
New-ADOrganizationalUnit [-WhatIf] [-Confirm] [-AuthType <ADAuthType>] [-City <String>] [-Country <String>]
 [-Credential <PSCredential>] [-Description <String>] [-DisplayName <String>]
 [-Instance <ADOrganizationalUnit>] [-ManagedBy <ADPrincipal>] [-Name] <String> [-OtherAttributes <Hashtable>]
 [-PassThru] [-Path <String>] [-PostalCode <String>] [-ProtectedFromAccidentalDeletion <Boolean>]
 [-Server <String>] [-State <String>] [-StreetAddress <String>] [<CommonParameters>]
```

## DESCRIPTION
The New-ADOrganizationalUnit cmdlet creates a new Active Directory organizational unit.
You can set commonly used organizational unit property values by using the cmdlet parameters.
Property values that are not associated with cmdlet parameters can be set by using the OtherAttributes parameter.

You must set the Name parameter to create a new organizational unit.
When you do not specify the Path parameter, the cmdlet creates an organizational unit under the default NC head for the domain.

The following methods explain different ways to create an object by using this cmdlet.

Method 1: Use the New-ADOrganizationalUnit cmdlet, specify the required parameters, and set any additional property values by using the cmdlet parameters.

Method 2: Use a template to create the new object.
To do this, create a new organizational unit object or retrieve a copy of an existing organizational unit object and set the Instance parameter to this object.
The object provided to the Instance parameter is used as a template for the new object.
You can override property values from the template by setting cmdlet parameters.
For examples and more information, see the Instance parameter description for this cmdlet.

Method 3: Use the Import-CSV cmdlet with the New-ADOrganizationalUnit cmdlet to create multiple Active Directory organizational unit objects.
To do this, use the Import-CSV cmdlet to create the custom objects from a comma-separated value (CSV) file that contains a list of object properties.
Then pass these objects through the pipeline to the New-ADOrganizationalUnit cmdlet to create the organizational unit objects.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
C:\PS>New-ADOrganizationalUnit -Name UserAccounts -Path "DC=FABRIKAM,DC=COM"
```

Description

-----------

Creates a new OrganizationalUnit named 'UserAccounts' which is protected from accidental deletion.

### -------------------------- EXAMPLE 2 --------------------------
```
C:\PS>New-ADOrganizationalUnit -Name UserAccounts -Path "DC=FABRIKAM,DC=COM" -ProtectedFromAccidentalDeletion $false
```

Description

-----------

Creates a new OrganizationalUnit named 'UserAccounts' which is not protected from deletion.

### -------------------------- EXAMPLE 3 --------------------------
```
C:\PS>New-ADOrganizationalUnit -Name UserAccounts -Path "DC=FABRIKAM,DC=COM" -OtherAttributes @{seeAlso="CN=HumanResourceManagers,OU=Groups,OU=Managed,DC=Fabrikam,DC=com";managedBy="CN=TomC,DC=FABRIKAM,DC=COM"}
```

Description

-----------

Creates an OrganizationalUnit name 'UserAccounts' which is protected from accidental deletion with properties 'seeAlso' and 'managedBy' set to the specified values.

### -------------------------- EXAMPLE 4 --------------------------
```
C:\PS>$ouTemplate = Get-ADOrganizationalUnit "OU=UserAccounts,DC=Fabrikam,DC=com" -properties seeAlso,managedBy; New-ADOrganizationalUnit -name TomCReports -instance $ouTemplate
```

Description

-----------

Uses the data from the OrganizationalUnit 'OU=UserAccounts,DC=Fabrikam,DC=com' as a template for another new OrganizationalUnit.

### -------------------------- EXAMPLE 5 --------------------------
```
C:\PS>New-ADOrganizationalUnit -name "Managed" -path "DC=AppNC" -server "FABRIKAM-SRV1:60000"
```

Description

-----------

Creates a new OrganizationalUnit named 'Managed' in an LDS instance.

## PARAMETERS

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
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Instance
Specifies an instance of an organizational unit object to use as a template for a new organizational unit object.

You can use an instance of an existing organizational unit object as a template or you can construct a new organizational unit object by using the Windows PowerShell command line or by using a script.
The following examples show how to use these two methods to create organizational unit object templates.

Method 1: Use an existing organizational unit object as a template for a new object.
To retrieve an instance of an existing organizational unit object use Get-ADOrganizationalUnit.
Then provide this object to the Instance parameter of the New-ADOrganizationalUnit cmdlet to create a new organizational unit object.
You can override property values of the new object by setting the appropriate parameters.

$organizationalUnitInstance = Get-ADOrganizationalUnit -Identity accountingAsia

New-ADOrganizationalUnit -Name accountingAustralia  -Instance $OrganizationalUnitInstance -Country Australia

Method 2: Create a new ADOrganizationalUnit object and set the property values by using the Windows PowerShell command line interface.
Then pass this object to the Instance parameter of the New-ADOrganizationalUnit cmdlet to create the new Active Directory organizational unit object.

$OrganizationalUnitInstance = new-object Microsoft.ActiveDirectory.Management.ADOrganizationalUnit

$OrganizationalUnitInstance.Country = Australia

New-ADOrganizationalUnit -Name accountingAustralia  -Instance $OrganizationalUnitInstance

Note: Specified attributes are not validated, so attempting to set attributes that do not exist or cannot be set will raise an error.

```yaml
Type: ADOrganizationalUnit
Parameter Sets: (All)
Aliases: 

Required: False
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
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the name of the object.
This parameter sets the Name property of the Active Directory object.
The LDAP Display Name (ldapDisplayName) of this property is "name".

The following example shows how to set this parameter to a name string.

-Name "SaraDavis"

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -OtherAttributes
Specifies object attribute values for attributes that are not represented by cmdlet parameters.
You can set one or more parameters at the same time with this parameter.
If an attribute takes more than one value, you can assign multiple values.
To identify an attribute, specify the LDAPDisplayName (ldapDisplayName) defined for it in the Active Directory schema.

Syntax:

To specify a single value for an attribute:

-OtherAttributes @{'AttributeLDAPDisplayName'=value}

To specify multiple values for an attribute

-OtherAttributes @{'AttributeLDAPDisplayName'=value1,value2,...}

You can specify values for more than one attribute by using semicolons to separate attributes. 
The following syntax shows how to set values for multiple attributes:

-OtherAttributes @{'Attribute1LDAPDisplayName'=value; 'Attribute2LDAPDisplayName'=value1,value2;...}

The following examples show how to use this parameter.

To set the value of a custom attribute called favColors that takes a set of Unicode strings, use the following syntax:

-OtherAttributes @{'favColors'="pink","purple"}

To set values for favColors and dateOfBirth simultaneously, use the following syntax:

-OtherAttributes @{'favColors'="pink","purple"; 'dateOfBirth'=" 01/01/1960"}

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

### -Path
Specifies the X.500 path of the Organizational Unit (OU) or container where the new object is created.

In many cases, a default value will be used for the Path parameter if no value is specified. 
The rules for determining the default value are given below. 
Note that rules listed first are evaluated first and once a default value can be determined, no further rules will be evaluated.

In AD DS environments, a default value for Path will be set in the following cases:

- If the cmdlet is run from an Active Directory PowerShell provider drive, the parameter is set to the current path of the provider drive.
- If the cmdlet has a default path, this will be used.  For example: in New-ADUser, the Path parameter would default to the Users container.
- If none of the previous cases apply, the default value of Path will be set to the default partition or naming context of the target domain.

In AD LDS environments, a default value for Path will be set in the following cases:

- If the cmdlet is run from an Active Directory PowerShell provider drive, the parameter is set to the current path of the provider drive.
- If the cmdlet has a default path, this will be used.  For example: in New-ADUser, the Path parameter would default to the Users container.
- If the target AD LDS instance has a default naming context, the default value of Path will be set to the default naming context.  To specify a default naming context for an AD LDS environment, set the msDS-defaultNamingContext property of the Active Directory directory service agent (DSA) object (nTDSDSA) for the AD LDS instance.
- If none of the previous cases apply, the Path parameter will not take any default value.

The following example shows how to set this parameter to an OU.

-Path "ou=mfg,dc=noam,dc=corp,dc=contoso,dc=com"

Note:  The Active Directory Provider cmdlets, such New-Item, Remove-Item, Remove-ItemProperty, Rename-Item and Set-ItemProperty also contain a Path property.
However, for the provider cmdlets, the Path parameter identifies the path of the actual object and not the container as with the Active Directory cmdlets.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: $true
Accept pipeline input: True (ByPropertyName)
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
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### None or Microsoft.ActiveDirectory.Management.ADOrganizationalUnit
An organizational unit object that is a template for the new organizational unit object is received by the Instance parameter.

## OUTPUTS

### None or Microsoft.ActiveDirectory.Management.ADOrganizationalUnit
Returns the new organizational unit object when the PassThru parameter is specified.
By default, this cmdlet does not generate any output.

## NOTES
* This cmdlet does not work with an Active Directory Snapshot.

  This cmdlet does not work with a read-only domain controller.

## RELATED LINKS

[Get-ADOrganizationalUnit](./Get-ADOrganizationalUnit.md)

[Remove-ADOrganizationalUnit](./Remove-ADOrganizationalUnit.md)

[Set-ADOrganizationalUnit](./Set-ADOrganizationalUnit.md)

