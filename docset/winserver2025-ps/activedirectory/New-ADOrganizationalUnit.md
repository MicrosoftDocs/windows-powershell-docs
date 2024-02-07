---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.ActiveDirectory.Management.dll-Help.xml
Module Name: ActiveDirectory
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/activedirectory/new-adorganizationalunit?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-ADOrganizationalUnit
---

# New-ADOrganizationalUnit

## SYNOPSIS

Creates an Active Directory organizational unit.

## SYNTAX

```
New-ADOrganizationalUnit [-WhatIf] [-Confirm] [-AuthType <ADAuthType>] [-City <String>] [-Country <String>]
 [-Credential <PSCredential>] [-Description <String>] [-DisplayName <String>]
 [-Instance <ADOrganizationalUnit>] [-ManagedBy <ADPrincipal>] [-Name] <String> [-OtherAttributes <Hashtable>]
 [-PassThru] [-Path <String>] [-PostalCode <String>] [-ProtectedFromAccidentalDeletion <Boolean>]
 [-Server <String>] [-State <String>] [-StreetAddress <String>] [<CommonParameters>]
```

## DESCRIPTION

The **New-ADOrganizationalUnit** cmdlet creates an Active Directory organizational unit (OU).
You can set commonly used OU property values by using the cmdlet parameters.
**Property** values that are not associated with cmdlet parameters can be set by using the *OtherAttributes* parameter.

You must set the *Name* parameter to create a new OU.
If you do not specify the *Path* parameter, the cmdlet creates an OU under the default naming context (NC) head for the domain.

The following methods describe how to create an object by using this cmdlet.

Method 1: Use the **New-ADOrganizationalUnit** cmdlet, specify the required parameters, and set any additional property values by using the cmdlet parameters.

Method 2: Use a template to create the new object.
To do this, create a new OU object or get a copy of an existing OU object and set the *Instance* parameter to this object.
The object provided to the *Instance* parameter is used as a template for the new object.
You can override property values from the template by setting cmdlet parameters.
For more information, see the *Instance* parameter description for this cmdlet.

Method 3: Use the **Import-Csv** cmdlet with the **New-ADOrganizationalUnit** cmdlet to create multiple Active Directory OU objects.
To do this, use the [**Import-Csv**](/powershell/module/microsoft.powershell.utility/import-csv) cmdlet to create the custom objects 
from a comma-separated value (CSV) file that contains a list of object properties.
Then pass these objects through the pipeline to the **New-ADOrganizationalUnit** cmdlet to create the OU objects.

## EXAMPLES

### Example 1: Create an OU

```
PS C:\> New-ADOrganizationalUnit -Name "UserAccounts" -Path "DC=FABRIKAM,DC=COM"
```

This command creates an OU named UserAccounts that is protected from accidental deletion. Note that accidental protection is implicit.

### Example 2: Create an OU that is not protected from accidental deletion

```
PS C:\> New-ADOrganizationalUnit -Name "UserAccounts" -Path "DC=FABRIKAM,DC=COM" -ProtectedFromAccidentalDeletion $False
```

This command creates an OU named UserAccounts that is not protected from accidental deletion.

### Example 3: Create an OU that is protected from accidental deletion

```
PS C:\> New-ADOrganizationalUnit -Name "UserAccounts" -Path "DC=FABRIKAM,DC=COM" -OtherAttributes @{seeAlso="CN=HumanResourceManagers,OU=Groups,OU=Managed,DC=Fabrikam,DC=com";managedBy="CN=TomC,DC=FABRIKAM,DC=COM"}
```

This command creates an OU named UserAccounts that is protected from accidental deletion.
The **seeAlso** and **managedBy** properties are set to specified values.

### Example 4: Create an OU from a template OU

```
PS C:\> $OuTemplate = Get-ADOrganizationalUnit -Identity "OU=UserAccounts,DC=Fabrikam,DC=com" -Properties seeAlso,managedBy 
PS C:\> New-ADOrganizationalUnit -Name "TomCReports" -Instance $OuTemplate
```

This command uses the data from the OU OU=UserAccounts,DC=Fabrikam,DC=com as a template for another OU.

### Example 5: Create an OU in an AD LDS instance

```
PS C:\> New-ADOrganizationalUnit -Name "Managed" -Path "DC=AppNC" -Server "FABRIKAM-SRV1:60000"
```

This command creates an OU named Managed in an AD LDS instance.

## PARAMETERS

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

### -City

Specifies the town or city.
This parameter sets the **City** property of an OU object.
The Lightweight Directory Access Protocol (LDAP) display name (**ldapDisplayName**) of this property is `l`.

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

Specifies the country or region code.
This parameter sets the **Country** property of an OU object.
The LDAP display name (**ldapDisplayName**) of this property is `c`.
This value is not used by Windows 2000.

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

To specify this parameter, you can type a user name, such as `User1` or `Domain01\User01` or you can specify a **PSCredential** object.
If you specify a user name for this parameter, the cmdlet prompts for a password.

You can also create a **PSCredential** object by using a script or by using the [Get-Credential](/powershell/module/microsoft.powershell.security/get-credential?view=powershell-7.3) cmdlet.
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
This parameter sets the value of the **Description** property for the OU object.
The LDAP display name (**ldapDisplayName**) for this property is `description`.

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
This parameter sets the **DisplayName** property of the OU object.
The LDAP display name (**ldapDisplayName**) for this property is `displayName`.

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

Specifies an instance of an OU object to use as a template for a new OU object.

You can use an instance of an existing OU object as a template or you can construct a new OU object by using the Windows PowerShell command line or by using a script.

Method 1: Use an existing OU object as a template for a new object.
To retrieve an instance of an existing OU object use Get-ADOrganizationalUnit.
Then provide this object to the *Instance* parameter of the **New-ADOrganizationalUnit** cmdlet to create a new OU object.
You can override property values of the new object by setting the appropriate parameters.

Method 2: Create a new **ADOrganizationalUnit** object and set the property values by using the Windows PowerShell command line interface.
Then pass this object to the *Instance* parameter of the **New-ADOrganizationalUnit** cmdlet to create the new Active Directory OU object.

> [!NOTE]
> Specified attributes are not validated, so attempting to set attributes that do not exist or cannot be set raises an error.

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
The acceptable values for this parameter are:

- A distinguished name
- A GUID (objectGUID)
- A security identifier (objectSid)
- A SAM account name (sAMAccountName)

This parameter sets the Active Directory attribute with an LDAP display name of `managedBy`.

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
This parameter sets the **Name** property of the OU object.
The LDAP display name (**ldapDisplayName**) of this property is `name`.

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
To identify an attribute, specify the LDAP display name (**ldapDisplayName**) defined for it in the Active Directory schema.

To specify a single value for an attribute:

`-OtherAttributes @{'AttributeLDAPDisplayName'=value}`

To specify multiple values for an attribute, separate the values with a comma:

`-OtherAttributes @{'AttributeLDAPDisplayName'=value1,value2,...}`

To specify values for multiple attributes, separate the attributes with a semi-colon:

`-OtherAttributes @{'Attribute1LDAPDisplayName'=value; 'Attribute2LDAPDisplayName'=value1,value2;...}`

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

### -Path

Specifies the X.500 path of the OU or container where the new object is created.

In many cases, a default value is used for the *Path* parameter if no value is specified.
The rules for determining the default value are given below.
Note that rules listed first are evaluated first and when a default value can be determined, no further rules are evaluated.

In Active Directory Domain Services (AD DS) environments, a default value for *Path* is set in the following cases:

- If the cmdlet is run from an Active Directory PowerShell provider drive, the parameter is set to the current path of the provider drive.
- If the cmdlet has a default path, this is used. For example: in **New-ADUser**, the *Path* parameter defaults to the Users container.
- If none of the previous cases apply, the default value of *Path* is set to the default partition or naming context of the target domain.

In AD LDS environments, a default value for *Path* is set in the following cases:

- If the cmdlet is run from an Active Directory module for PowerShell provider drive, the parameter is set to the current path of the provider drive.
- If the cmdlet has a default path, this is used. For example: in **New-ADUser**, the *Path* parameter defaults to the Users container.
- If the target AD LDS instance has a default naming context, the default value of *Path* is set to the default naming context.
  To specify a default naming context for an AD LDS environment, set the **msDS-defaultNamingContext** property of the Active Directory directory service agent object (**nTDSDSA**) for the AD LDS instance.
- If none of the previous cases apply, the *Path* parameter does not take any default value.

> [!NOTE]
> The Active Directory Provider cmdlets, such as **New-Item**, **Remove-Item**, **Remove-ItemProperty**, **Rename-Item**, and **Set-ItemProperty**, also contain a **Path** property.
>
> However, for the Active Directory Provider cmdlets, the *Path* parameter identifies the path of the actual object rather than the container.

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

Specifies the postal code or zip code.
This parameter sets the **PostalCode** property of an OU object.
The LDAP display name (**ldapDisplayName**) of this property is `postalCode`.

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

Indicates whether to prevent the object from being deleted.
When this property is set to $True, you cannot delete the corresponding object without changing the value of the property.
The acceptable values for this parameter are:

- $False or 0
- $True or 1

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Server

Specifies the AD DS instance to connect to, by providing one of the following values for a corresponding domain name or directory server.
The service may be any of the following: AD LDS, AD DS, or Active Directory snapshot instance.

Specify the AD DS instance in one of the following ways:

Domain name values:

- Fully qualified domain name
- NetBIOS name

Directory server values:

- Fully qualified directory server name
- NetBIOS name
- Fully qualified directory server name and port

The default value for this parameter is determined by one of the following methods in the order that they are listed:

- By using the *Server* value from objects passed through the pipeline
- By using the server information associated with the AD DS Windows PowerShell provider drive, when the cmdlet runs in that drive
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

### -State

Specifies a state or province.
This parameter sets the **State** property of an OU object.
The LDAP display name (**ldapDisplayName**) of this property is `st`.

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

Specifies a street address.
This parameter sets the **StreetAddress** property of an OU object.
The LDAP display name (**ldapDisplayName**) of this property is `street`.

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

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None or Microsoft.ActiveDirectory.Management.ADOrganizationalUnit

An OU object that is a template for the new OU object is received by the *Instance* parameter.

## OUTPUTS

### None or Microsoft.ActiveDirectory.Management.ADOrganizationalUnit

Returns the new OU object when the *PassThru* parameter is specified.
By default, this cmdlet does not generate any output.

## NOTES

* This cmdlet does not work with an Active Directory snapshot.
* This cmdlet does not work with a read-only domain controller.

## RELATED LINKS

[Get-ADOrganizationalUnit](./Get-ADOrganizationalUnit.md)

[Remove-ADOrganizationalUnit](./Remove-ADOrganizationalUnit.md)

[Set-ADOrganizationalUnit](./Set-ADOrganizationalUnit.md)
