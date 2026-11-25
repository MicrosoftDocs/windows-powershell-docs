---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.ActiveDirectory.Management.dll-Help.xml
Module Name: ActiveDirectory
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/activedirectory/new-adobject?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-ADObject
---

# New-ADObject

## SYNOPSIS
Creates an Active Directory object.

## SYNTAX

```
New-ADObject [-WhatIf] [-Confirm] [-AuthType <ADAuthType>] [-Credential <PSCredential>] [-Description <String>]
 [-DisplayName <String>] [-Instance <ADObject>] [-Name] <String> [-OtherAttributes <Hashtable>] [-PassThru]
 [-Path <String>] [-ProtectedFromAccidentalDeletion <Boolean>] [-Server <String>] [-Type] <String>
 [<CommonParameters>]
```

## DESCRIPTION
The **New-ADObject** cmdlet creates an Active Directory object such as a new organizational unit (OU) or new user account.
You can use this cmdlet to create any type of Active Directory object.
Many object properties are defined by setting cmdlet parameters.
Properties that are not set by cmdlet parameters can be set by using the *OtherAttributes* parameter.

You must set the *Name* and *Type* parameters to create a new Active Directory object.
The *Name* specifies the name of the new object.
The *Type* parameter specifies the Lightweight Directory Access Protocol (LDAP) display name of the Active Directory schema class that represents the type of object you want to create.
Examples of *Type* values include computer, group, OU, and user.

The *Path* parameter specifies the container where the object is created.
If you do not specify the *Path* parameter, the cmdlet creates an object in the default naming context container for Active Directory objects in the domain.

The following methods explain different ways to create an object by using this cmdlet.

Method 1: Use the **New-ADObject** cmdlet, specify the required parameters, and set any additional property values by using the cmdlet parameters.

Method 2: Use a template to create the new object.
To do this, create a new Active Directory object or retrieve a copy of an existing Active Directory object and set the *Instance* parameter to this object.
The object provided to the *Instance* parameter is used as a template for the new object.
You can override property values from the template by setting cmdlet parameters.
For more information, see the *Instance* parameter description for this cmdlet.

Method 3: Use the Import-Csv cmdlet with the **New-ADObject** cmdlet to create multiple Active Directory objects.
To do this, use the **Import-CSV** cmdlet to create the custom objects from a comma-separated value (CSV) file that contains a list of object properties.
Then pass these objects through the pipeline to the **New-ADObject** cmdlet to create the Active Directory objects.

## EXAMPLES

### Example 1: Create a subnet object
```
PS C:\> New-ADObject -Name "192.168.1.0/26" -Type "subnet" -Description "192.168.1.0/255.255.255.192" -OtherAttributes @{location="Building A";siteObject="CN=HQ,CN=Sites,CN=Configuration,DC=FABRIKAM,DC=COM"} -Path "CN=Subnets,CN=Sites,CN=Configuration,DC=FABRIKAM,DC=COM"
```

This command creates a subnet object in the HQ site with the described attributes.

### Example 2: Create a subnet object by template
```
PS C:\> $SubnetTemplate = Get-ADObject -Identity "CN=192.168.1.0/26,CN=Subnets,CN=Sites,CN=Configuration,DC=Fabrikam,DC=com" -Properties description,location
PS C:\> New-ADObject -Instance $SubnetTemplate -Name "192.168.1.0/28" -Type "subnet" -Path "CN=Subnets,CN=Sites,CN=Configuration,DC=FABRIKAM,DC=COM"
```

This example creates a new subnet object, using a different subnet object as a template.

### Example 3: Create a contact object
```
PS C:\> New-ADObject -Name "SaraDavisContact" -Type "contact" -ProtectedFromAccidentalDeletion $True -OtherAttributes @{'msDS-SourceObjectDN'="CN=FabrikamContacts,DC=CONTOSO,DC=COM"}
```

This command creates a new contact object, sets the **msDS-SourceObjectDN** property and protects the object from accidental deletion.

### Example 4: Create a container object
```
PS C:\> New-ADObject -Name "Apps" -Type "container" -Path "DC=AppNC" -Server "FABRIKAM-SRV1:60000"
```

This command creates a new container object named Apps in an AD LDS instance.

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
This parameter sets the **DisplayName** property of the object.
The LDAP display name (**ldapDisplayName**) for this property is displayName.

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
Specifies an instance of an Active Directory object to use as a template for a new Active Directory object.

You can use an instance of an existing Active Directory object as a template or you can construct a new Active Directory object by using the Windows PowerShell command line or by using a script.

Method 1: Use an existing Active Directory object as a template for a new object.
To retrieve an instance of an existing Active Directory object, use a cmdlet such as **Get-ADObject**.
Then provide this object to the *Instance* parameter of the **New-ADObject** cmdlet to create a new Active Directory object.
You can override property values of the new object by setting the appropriate parameters.

Method 2: Create a new **ADObject** and set the property values by using the Windows PowerShell command line interface.
Then pass this object to the *Instance* parameter of the **New-ADObject** cmdlet to create the new Active Directory object.

Note: Specified attributes are not validated, so attempting to set attributes that do not exist or cannot be set raises an error.

```yaml
Type: ADObject
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of the object.
This parameter sets the **Name** property of the Active Directory object.
The LDAP display name (**ldapDisplayName**) of this property is name.

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

To specify multiple values for an attribute:

`-OtherAttributes @{'AttributeLDAPDisplayName'=value1,value2,...}`

To specify values for multiple attributes:

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

In AD DS environments, a default value for *Path* will be set in the following cases:

- If the cmdlet is run from an Active Directory PowerShell provider drive, the parameter is set to the current path of the provider drive.
- If the cmdlet has a default path, this is used.
For example: in New-ADUser, the *Path* parameter defaults to the Users container.
- If none of the previous cases apply, the default value of *Path* is set to the default partition or naming context of the target domain.

In AD LDS environments, a default value for *Path* is set in the following cases:

- If the cmdlet is run from an Active Directory module for PowerShell provider drive, the parameter is set to the current path of the provider drive.
- If the cmdlet has a default path, this is used.
For example: in New-ADUser, the *Path* parameter defaults to the Users container.
- If the target AD LDS instance has a default naming context, the default value of *Path* is set to the default naming context.
To specify a default naming context for an AD LDS environment, set the **msDS-defaultNamingContext** property of the Active Directory directory service agent object (**nTDSDSA**) for the AD LDS instance.
- If none of the previous cases apply, the *Path* parameter does not take any default value.

Note: The Active Directory Provider cmdlets, such as **New-Item**, **Remove-Item**, **Remove-ItemProperty**, **Rename-Item**, and **Set-ItemProperty**, also contain a *Path* property.
However, for the Active Directory Provider cmdlets, the *Path* parameter identifies the path of the actual object rather than the container.

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
Specifies the Active Directory Domain Services (AD DS) instance to connect to, by providing one of the following values for a corresponding domain name or directory server.
The service may be any of the following: Active Directory Lightweight Directory Services (AD LDS), AD DS, or Active Directory snapshot instance.

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

### -Type
Specifies the type of object to create.
Set the *Type* parameter to the LDAP display name of the Active Directory schema class that represents the type of object that you want to create.
Examples of type values include user, computer, and group.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 2
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

### None or Microsoft.ActiveDirectory.Management.ADObject
An Active Directory object that is a template for the new object is received by the *Instance* parameter.

Derived types, such as the following, are also accepted:

- **Microsoft.ActiveDirectory.Management.ADPartition**
- **Microsoft.ActiveDirectory.Management.ADFineGrainedPasswordPolicy**
- **Microsoft.ActiveDirectory.Management.ADGroup**
- **Microsoft.ActiveDirectory.Management.ADUser**
- **Microsoft.ActiveDirectory.Management.ADComputer**

## OUTPUTS

### None or Microsoft.ActiveDirectory.Management.ADObject
Returns the new Active Directory object when the *PassThru* parameter is specified.
By default, this cmdlet does not generate any output.

## NOTES
* This cmdlet does not work with an Active Directory snapshot.
* This cmdlet does not work with a read-only domain controller.

## RELATED LINKS

[Get-ADObject](./Get-ADObject.md)

[Move-ADObject](./Move-ADObject.md)

[Remove-ADObject](./Remove-ADObject.md)

[Rename-ADObject](./Rename-ADObject.md)

[Restore-ADObject](./Restore-ADObject.md)

[Set-ADObject](./Set-ADObject.md)

[Sync-ADObject](./Sync-ADObject.md)

