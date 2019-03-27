---
external help file: Microsoft.ActiveDirectory.Management.dll-Help.xml
ms.assetid: 96C6614D-C050-4706-B727-D61D43B115B8
manager: dansimp
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: kenwith
author: kenwith
---

# Set-ADGroup

## SYNOPSIS
Modifies an Active Directory group.

## SYNTAX

### Identity
```
Set-ADGroup [-WhatIf] [-Confirm] [-Add <Hashtable>] [-AuthType <ADAuthType>] [-Clear <String[]>]
 [-Credential <PSCredential>] [-Description <String>] [-DisplayName <String>]
 [-GroupCategory <ADGroupCategory>] [-GroupScope <ADGroupScope>] [-HomePage <String>] [-Identity] <ADGroup>
 [-ManagedBy <ADPrincipal>] [-Partition <String>] [-PassThru] [-Remove <Hashtable>] [-Replace <Hashtable>]
 [-SamAccountName <String>] [-Server <String>] [<CommonParameters>]
```

### Instance
```
Set-ADGroup [-WhatIf] [-Confirm] [-AuthType <ADAuthType>] [-Credential <PSCredential>] -Instance <ADGroup>
 [-PassThru] [-Server <String>] [<CommonParameters>]
```

## DESCRIPTION
The Set-ADGroup cmdlet modifies the properties of an Active Directory group.
You can modify commonly used property values by using the cmdlet parameters.
Property values that are not associated with cmdlet parameters can be modified by using the Add, Replace, Clear and Remove parameters.

The Identity parameter specifies the Active Directory group to modify.
You can identify a group by its distinguished name (DN), GUID, security identifier (SID) or Security Accounts Manager (SAM) account name.
You can also set the Identity parameter to an object variable such as $\<localGroupObject\>, or you can pass a group object through the pipeline to the Identity parameter.
For example, you can use the Get-ADGroup cmdlet to retrieve a group object and then pass the object through the pipeline to the Set-ADGroup cmdlet.

The Instance parameter provides a way to update a group object by applying the changes made to a copy of the object.
When you set the Instance parameter to a copy of an Active Directory group object that has been modified, the Set-ADGroup cmdlet makes the same changes to the original group object.
To get a copy of the object to modify, use the Get-ADGroup object.
The Identity parameter is not allowed when you use the Instance parameter.
For more information about the Instance parameter, see the Instance parameter description.
For more information about how the Instance concept is used in Active Directory cmdlets, see about_ActiveDirectory_Instance

The following examples show how to modify the Description property of a group object by using three methods:

-By specifying the Identity and the Description parameters

-By passing a group object through the pipeline and specifying the Description parameter

-By specifying the Instance parameter.

Method 1: Modify the Description property for the SecurityLevel2Access group by using the Identity and Description parameters.

Set-ADGroup -Identity SecurityLevel2Access -Description "Used to authorize Security Level 2 access."

Method 2: Modify the Description property for the SecurityLevel2Access group by passing the SecurityLevel2Access group through the pipeline and specifying the Description parameter.

Get-ADGroup -Identity "SecurityLevel2Access" | Set-ADGroup -Description "Used to authorize Security Level 2 access."

Method 3: Modify the \<property\> property for the SecurityLevel2Access group by using the Windows PowerShell command line to modify a local instance of the SecurityLevel2Access group.
Then set the Instance parameter to the local instance.

$group = Get-ADGroup -Identity "SecurityLevel2Access"

$group.Description = "Used to authorize Security Level 2 access."

Set-ADGroup -Instance $group.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
C:\PS>set-adgroup -server localhost:60000 -Identity "CN=AccessControl,DC=AppNC" -description "Access Group" -passthru


DistinguishedName : CN=AccessControl,DC=AppNC
GroupCategory     : Security
GroupScope        : DomainLocal
Name              : AccessControl
ObjectClass       : group
ObjectGUID        : d65f5e8f-36da-4390-9840-8b9fde6282fc
SID               : S-1-510474493-936115905-2782881406-1264922549-3814061485-1557022459
```

Description

-----------

Set the description property of the group AccessControl to "Access Group" on an ADAM instance.

### -------------------------- EXAMPLE 2 --------------------------
```
C:\PS>get-adgroup -filter 'name -like "Access*"' | set-adgroup -description "Access Group"
```

Description

-----------

Modify the description on all groups that have a name that starts with access via the pipeline.

### -------------------------- EXAMPLE 3 --------------------------
```
C:\PS>PS adam:\DC=AppNC> get-adgroup -filter 'name -like "Access*"' | set-adgroup -description "Access Group"
PS adam:\DC=AppNC> $group = get-adgroup -server localhost:60000 -Identity "CN=AccessControl,DC=AppNC"
PS adam:\DC=AppNC> $group.description = "Access Group"
PS adam:\DC=AppNC> set-adgroup -Instance $group -passthru

DistinguishedName : CN=AccessControl,DC=AppNC
GroupCategory     : Security
GroupScope        : DomainLocal
Name              : AccessControl
ObjectClass       : group
ObjectGUID        : d65f5e8f-36da-4390-9840-8b9fde6282fc
SID               : S-1-510474493-936115905-2782881406-1264922549-3814061485-1557022459
```

Description

-----------

Set the description property on the AccessControl group via the instance parameter.

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
Parameter Sets: Identity
Aliases: 
Accepted values: Distribution, Security

Required: False
Position: Named
Default value: Security
Accept pipeline input: False
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
Parameter Sets: Identity
Aliases: 
Accepted values: DomainLocal, Global, Universal

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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
Parameter Sets: Identity
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Identity
Specifies an Active Directory group object by providing one of the following values.
The identifier in parentheses is the LDAP display name for the attribute.

Distinguished Name

Example: CN=saradavisreports,OU=europe,CN=users,DC=corp,DC=contoso,DC=com

GUID (objectGUID)

Example: 599c3d2e-f72d-4d20-8a88-030d99495f20

Security Identifier (objectSid)

Example: S-1-5-21-3165297888-301567370-576410423-1103

Security Accounts Manager (SAM) Account Name (sAMAccountName)

Example: saradavisreports

The cmdlet searches the default naming context or partition to find the object.
If two or more objects are found, the cmdlet returns a non-terminating error.

This parameter can also get this object through the pipeline or you can set this parameter to an object instance.

This example shows how to set the parameter to a distinguished name.

-Identity  "CN=saradavisreports,OU=europe,CN=users,DC=corp,DC=contoso,DC=com"

This example shows how to set this parameter to a group object instance named "ADGroupInstance".

-Identity $ADGroupInstance

```yaml
Type: ADGroup
Parameter Sets: Identity
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Instance
Specifies a modified copy of a group object to use to update the actual Active Directory group object.
When this parameter is used, any modifications made to the modified copy of the object are also made to the corresponding Active Directory object.
The cmdlet only updates the object properties that have changed.

The Instance parameter can only update group objects that have been retrieved by using the Get-ADGroup cmdlet.
When you specify the Instance parameter, you cannot specify other parameters that set properties on the object.

The following is an example of how to use the Get-ADGroup cmdlet to retrieve an instance of the ADGroup object.
The object is modified by using the Windows PowerShell command line.
Then the Set-ADGroup cmdlet saves the changes to the Active Directory object.

Step 1: Retrieve a local instance of the object.

$groupInstance = Get-ADGroup  -Identity "SaraDavisReports"

Step 2: Modify one or more properties of the object instance.

$groupInstance.GroupScope= "Global"

Step3: Save your changes to "SaraDavisReports".

Set-ADGroup -Instance $groupInstance

```yaml
Type: ADGroup
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
You can modify more than one property by specifying a comma-separated list.
The format for this parameter is

-Replace @{Attribute1LDAPDisplayName=value\[\],   Attribute2LDAPDisplayName=value\[\]}

For example, if you want to replace the value "555-222-2222" with the values "555-222-1111" for Phone-Office-Other attribute (LDAP display name 'otherTelephone') set the Replace parameter as follows.

-Replace @{otherTelephone='555-222-2222', '555-222-1111'}

When you use the Add, Remove, Replace  and Clear parameters together, the operations will be performed in the following order:

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
A group object is received by the Identity parameter.

A group object that was retrieved by using the Get-ADGroup cmdlet and then modified is received by the Instance parameter.

## OUTPUTS

### None or Microsoft.ActiveDirectory.Management.ADGroup
Returns the modified group object when the PassThru parameter is specified.
By default, this cmdlet does not generate any output.

## NOTES
* This cmdlet does not work with an Active Directory Snapshot.

  This cmdlet does not work with a read-only domain controller.

## RELATED LINKS

[Add-ADGroupMember](./Add-ADGroupMember.md)

[Add-ADPrincipalGroupMembership](./Add-ADPrincipalGroupMembership.md)

[Get-ADGroup](./Get-ADGroup.md)

[Get-ADGroupMember](./Get-ADGroupMember.md)

[Get-ADPrincipalGroupMembership](./Get-ADPrincipalGroupMembership.md)

[New-ADGroup](./New-ADGroup.md)

[Remove-ADGroup](./Remove-ADGroup.md)

[Remove-ADGroupMember](./Remove-ADGroupMember.md)

[Remove-ADPrincipalGroupMembership](./Remove-ADPrincipalGroupMembership.md)

