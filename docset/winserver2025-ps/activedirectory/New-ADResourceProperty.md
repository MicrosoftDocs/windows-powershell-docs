---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.ActiveDirectory.Management.dll-Help.xml
Module Name: ActiveDirectory
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/activedirectory/new-adresourceproperty?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-ADResourceProperty
---

# New-ADResourceProperty

## SYNOPSIS
Creates a resource property in Active Directory.

## SYNTAX

```
New-ADResourceProperty [-WhatIf] [-Confirm] [-AppliesToResourceTypes <String[]>] [-AuthType <ADAuthType>]
 [-Credential <PSCredential>] [-Description <String>] [-DisplayName] <String> [-Enabled <Boolean>]
 [-ID <String>] [-Instance <ADResourceProperty>] [-IsSecured <Boolean>] [-OtherAttributes <Hashtable>]
 [-PassThru] [-ProtectedFromAccidentalDeletion <Boolean>]
 -ResourcePropertyValueType <ADResourcePropertyValueType> [-Server <String>] [-SharesValuesWith <ADClaimType>]
 [-SuggestedValues <ADSuggestedValueEntry[]>] [<CommonParameters>]
```

## DESCRIPTION
The **New-ADResourceProperty** cmdlet creates a resource property in the directory.

## EXAMPLES

### Example 1: Create a resource property
```
PS C:\> New-ADResourceProperty -DisplayName "Authors" -ResourcePropertyValueType MS-DS-MultivaluedText
```

This command creates a resource property with the display name Authors.
The resource property enables the names of multiple authors to be specified.

### Example 2: Create a resource property to include suggested values
```
PS C:\> $US = New-Object Microsoft.ActiveDirectory.Management.ADSuggestedValueEntry("US", "United States of America", "United States of America")
PS C:\> $JP = New-Object Microsoft.ActiveDirectory.Management.ADSuggestedValueEntry("JP", "Japan", "Japan")
PS C:\> New-ADResourceProperty -DisplayName "Country" -ResourcePropertyValueType MS-DS-MultivaluedChoice -SuggestedValues $US,$JP
```

This command creates a new resource property with display name Country.
The suggested values are set to US and JP.
Applications using this resource property would allow their users to specify one of the suggested values as this resource property's value.

### Example 3: Create a resource property with shared values
```
PS C:\> New-ADResourceProperty -DisplayName "Country" -ResourcePropertyValueType MS-DS-MultivaluedChoice -SharesValuesWith Country
```

This command creates a reference resource property with the display name Country.
It uses an existing claim type named Country for its suggested values.
This enables the resource property to be always valid for comparisons with the referenced claim type in a central access rule.

### Example 4: Create a multivalued text resource property
```
PS C:\> New-ADResourceProperty -DisplayName "Authors" -ResourcePropertyValueType MS-DS-MultivaluedText -ID "Authors_60DB20331638"
```

This command creates a resource property with the display name Authors, and sets its ID to Authors_60DB20331638.

The ID should only be set manually in a multi-forest environment where the same resource property must work across forests.
By default, **New-ADResourceProperty** generates the ID automatically.
For resource properties to be considered identical across forests, their ID must be the same.

## PARAMETERS

### -AppliesToResourceTypes
Specifies the resource types to which this resource property is applied.

```yaml
Type: String[]
Parameter Sets: (All)
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
The LDAP Display Name (**ldapDisplayName**) for this property is description.

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
Specifies the display name of the resource property.
The display name of the resource property must be unique.

The display name of a resource property can be used as an identity in other Active Directory cmdlets.
For example, if the display name of a resource property is Country, then you can type `Get-ADResourceProperty -Identity "Country"` to get the resource property.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Enabled
Indicates whether the resource property is enabled.

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

### -ID
Specifies the resource property ID.
This is an optional parameter.
By default, New-ADResourceProperty generates the ID automatically.

The ID should only be set manually in a multi-forest environment where the same resource properties need to work across forests.
For resource properties to be considered identical across forests, their ID must be the same.

To specify the ID, the ID string must conform to the following format:

- Start with a prefix string of one to 15 characters in length.
- The prefix string must be followed by an underscore.
- The prefix string and underscore must be followed by a suffix string of 1 to 16 characters in length.
- All characters contained in either prefix or suffix strings must contain only valid filename characters.

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
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IsSecured
Indicates whether the resource property is secure.
Only secure resource properties can be used for authorization decisions or used within central access rules.
Unsecured resource properties cannot be used for these purposes.

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

### -OtherAttributes
Specifies object attribute values for attributes that are not represented by cmdlet parameters.
You can set one or more parameters at the same time with this parameter.
If an attribute takes more than one value, you can assign multiple values.
To identify an attribute, specify the LDAPDisplayName (**ldapDisplayName**) defined for it in the Active Directory schema.

To specify a single value for an attribute:

`-OtherAttributes @{'AttributeLDAPDisplayName'=value}`

To specify multiple values for an attribute

`-OtherAttributes @{'AttributeLDAPDisplayName'=value1,value2,...}`

You can specify values for more than one attribute by using semicolons to separate attributes.
The following syntax shows how to set values for multiple attributes:

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

### -ResourcePropertyValueType
Specifies the value type for a resource property.
When a resource property is passed to a resource manager (for example, File Server), the resource manager leverages the resource property value type to determine how to handle the resource property.

You can use the Get-ADResourcePropertyValueType cmdlet to get the list of resource property value types.

Below is a list of the built-in resource property value types available in Active Directory:

- MS-DS-SinglevaluedChoice
- MS-DS-YesNo
- MS-DS-Number
- MS-DS-DateTime
- MS-DS-OrderedList
- MS-DS-Text
- MS-DS-MultivaluedText
- MS-DS-MultivaluedChoice

```yaml
Type: ADResourcePropertyValueType
Parameter Sets: (All)
Aliases:

Required: True
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

### -SharesValuesWith
Specifies a reference resource property.
Reference resource properties do not provide their own suggested values, but rather use the suggested values from the claim type object specified in this parameter.
This enables the resource property to always remain valid for use in comparisons to its referred claim type within a central access rule.

```yaml
Type: ADClaimType
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SuggestedValues
Specifies one or more suggested values for the resource property.
An application may choose to present this list of suggested values for the user to choose from.
When **RestrictValues** is set to $True, the application should restrict the user to pick values from this list only.

```yaml
Type: ADSuggestedValueEntry[]
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

### None or Microsoft.ActiveDirectory.Management.ADResourceProperty

## OUTPUTS

### None or Microsoft.ActiveDirectory.Management.ADResourceProperty

## NOTES
* This cmdlet does not work with an Active Directory Snapshot.
* This cmdlet does not work with a read-only domain controller.

## RELATED LINKS

[Get-ADResourceProperty](./Get-ADResourceProperty.md)

[Remove-ADResourceProperty](./Remove-ADResourceProperty.md)

[Set-ADResourceProperty](./Set-ADResourceProperty.md)

