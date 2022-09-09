---
external help file: Microsoft.ActiveDirectory.Management.dll-Help.xml
Module Name: ActiveDirectory
online version: https://docs.microsoft.com/powershell/module/activedirectory/new-adgroup?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# New-ADGroup

## SYNOPSIS
Creates an Active Directory group.

## SYNTAX

```
New-ADGroup [-WhatIf] [-Confirm] [-AuthType <ADAuthType>] [-Credential <PSCredential>] [-Description <String>]
 [-DisplayName <String>] [-GroupCategory <ADGroupCategory>] [-GroupScope] <ADGroupScope> [-HomePage <String>]
 [-Instance <ADGroup>] [-ManagedBy <ADPrincipal>] [-Name] <String> [-OtherAttributes <Hashtable>] [-PassThru]
 [-Path <String>] [-SamAccountName <String>] [-Server <String>] [<CommonParameters>]
```

## DESCRIPTION
The New-ADGroup cmdlet creates a new Active Directory group object.
Many object properties are defined by setting cmdlet parameters.
Properties that cannot be set by cmdlet parameters can be set using the OtherAttributes parameter.

The Name and GroupScope parameters specify the name and scope of the group and are required to create a new group.
You can define the new group as a security or distribution group by setting the GroupType parameter.
The Path parameter specifies the container or organizational unit (OU) for the group.

The following methods explain different ways to create an object by using this cmdlet.

Method 1: Use the New-ADGroup cmdlet, specify the required parameters, and set any additional property values by using the cmdlet parameters.

Method 2: Use a template to create the new object.
To do this, create a new group object or retrieve a copy of an existing group object and set the Instance parameter to this object.
The object provided to the Instance parameter is used as a template for the new object.
You can override property values from the template by setting cmdlet parameters.
For examples and more information, see the Instance parameter description for this cmdlet.

Method 3: Use the Import-CSV cmdlet with the New-ADGroup cmdlet to create multiple Active Directory group objects.
To do this, use the Import-CSV cmdlet to create the custom objects from a comma-separated value (CSV) file that contains a list of object properties.
Then pass these objects through the pipeline to the New-ADGroup cmdlet to create the group objects.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
C:\PS>New-ADGroup -Name "RODC Admins" -SamAccountName RODCAdmins -GroupCategory Security -GroupScope Global -DisplayName "RODC Administrators" -Path "CN=Users,DC=Fabrikam,DC=Com" -Description "Members of this group are RODC Administrators"
```

Description

-----------

Create a new group named 'RODC Admins' in the container 'CN=Users,DC=Fabrikam,DC=Com' and set the GroupCategory, DisplayName, GroupScope, and Description properties on the new object.

### -------------------------- EXAMPLE 2 --------------------------
```
C:\PS>Get-ADGroup FabrikamBranch1 -Properties Description | New-ADGroup  -Name Branch1Employees  -SamAccountName Branch1Employees -GroupCategory Distribution -PassThru


GroupScope        : Universal
Name              : Branch1Employees
GroupCategory     : Distribution
SamAccountName    : Branch1Employees
ObjectClass       : group
ObjectGUID        : 8eebce44-5df7-4bed-a98b-b987a702103e
SID               : S-1-5-21-41432690-3719764436-1984117282-1117
DistinguishedName : CN=Branch1Employees,CN=Users,DC=Fabrikam,DC=com
```

Description

-----------

Create a new group using the property values from a current group.

### -------------------------- EXAMPLE 3 --------------------------
```
C:\PS>New-ADGroup -Server localhost:60000 -Path "OU=AccountDeptOU,DC=AppNC" -Name AccountLeads -GroupScope DomainLocal  -GroupCategory Distribution
```

Description

-----------

Create a new group named 'AccountLeads' on an AD LDS instance.

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

### -GroupCategory
Specifies the category of the group.
Possible values of this parameter are:

Distribution or 0

Security or 1

This parameter sets the GroupCategory property of the group.
This parameter value combined with other group values sets the LDAP Display Name (ldapDisplayName) attribute named "groupType".

The following example shows how to specify that a group is a security group.

-GroupCategory security

```yaml
Type: ADGroupCategory
Parameter Sets: (All)
Aliases: 
Accepted values: Distribution, Security

Required: False
Position: Named
Default value: Security
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -GroupScope
Specifies the group scope of the group.
Possible values of this parameter are:

DomainLocal or 0

Global or 1

Universal or 2

This parameter sets the GroupScope property of a group object to the specified value.
The LDAP display name of this property is "groupType".

The following example shows two ways to set this parameter to DomainLocal.

-GroupScope DomainLocal

-GroupScope 0

```yaml
Type: ADGroupScope
Parameter Sets: (All)
Aliases: 
Accepted values: DomainLocal, Global, Universal

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -HomePage
Specifies the URL of the home page of the object.
This parameter sets the homePage property of an Active Directory object.
The LDAP Display Name (ldapDisplayName) for this property is "wWWHomePage".

The following example shows how to set this parameter to a URL.

-HomePage "http://employees.contoso.com/sdavis"

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
Specifies an instance of a group object to use as a template for a new group object.

You can use an instance of an existing group object as a template or you can construct a new group object by using the Windows PowerShell command line or by using a script.
The following examples show how to use these two methods to create group object templates.

Method 1: Use an existing group object as a template for a new object.
Use the Get-ADGroup cmdlet to retrieve a group object then pass this object to the Instance parameter of the New-ADGroup cmdlet to create a new group object.
You can override property values of the new object by setting the appropriate parameters.

$groupInstance = Get-ADGroup -Identity "KarenTohReports"

New-ADGroup -Name "Sara Davis Reports"  -Instance $groupInstance GroupType DomainLocal

Method 2: Create a new ADGroup object and set the property values by using the Windows PowerShell command line interface.
Then pass this object to the Instance parameter of the New-ADGroup cmdlet to create the new group object.

$groupTemplate = New-Object Microsoft.ActiveDirectory.Management.ADGroup

$groupTemplateGroupType = DomainLocal

New-ADGroup -Name "Sara Davis Reports" -Instance $groupInstance

Note: Specified attributes are not validated, so attempting to set attributes that do not exist or cannot be set will raise an error.

```yaml
Type: ADGroup
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

### -SamAccountName
Specifies the Security Account Manager (SAM) account name of the user, group, computer, or service account.
The maximum length of the description is 256 characters.
To be compatible with older operating systems, create a SAM account name that is 20 characters or less.
This parameter sets the SAMAccountName for an account object.
The LDAP display name (ldapDisplayName) for this property is "sAMAccountName".

The following example shows how to specify this parameter.

-SAMAccountName "saradavis"

Note: If the string value provided is not terminated with a '$' character, the system adds one if needed.

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

### None or Microsoft.ActiveDirectory.Management.ADGroup
A group object that is a template for the new group object is received by the Instance parameter.

## OUTPUTS

### None or Microsoft.ActiveDirectory.Management.ADGroup
Returns the new group object when the PassThru parameter is specified.
By default, this cmdlet does not generate any output.

## NOTES
* This cmdlet does not work with an Active Directory Snapshot.

  This cmdlet does not work with a read-only domain controller.

## RELATED LINKS

[Get-ADGroup](./Get-ADGroup.md)

[Remove-ADGroup](./Remove-ADGroup.md)

[Set-ADGroup](./Set-ADGroup.md)

[Import-CSV](/previous-versions/powershell/module/microsoft.powershell.utility/import-csv)
