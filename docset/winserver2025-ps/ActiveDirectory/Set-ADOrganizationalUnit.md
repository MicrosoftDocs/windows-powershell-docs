---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.ActiveDirectory.Management.dll-Help.xml
Module Name: ActiveDirectory
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/activedirectory/set-adorganizationalunit?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-ADOrganizationalUnit
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

### Example 1: Set a description for an OU
```
PS C:\> Set-ADOrganizationalUnit -Identity "OU=UserAccounts,DC=FABRIKAM,DC=COM" -Description "This Organizational Unit holds all of the users accounts of FABRIKAM.COM"
```

This command sets the description of the OU with the distinguished name OU=UserAccounts,DC=FABRIKAM,DC=COM.

### Example 2: Set the ProtectedFromAccidentalDeletion property for an OU
```
PS C:\> Set-ADOrganizationalUnit -Identity "OU=UserAccounts,DC=FABRIKAM,DC=COM" -ProtectedFromAccidentalDeletion $false
```

This command sets the **ProtectedFromAccidentalDeletion** property to $False on the OU with distinguished name OU=UserAccounts,DC=FABRIKAM,DC=COM.

### Example 3: Set location properties for an OU
```
PS C:\> Set-ADOrganizationalUnit -Identity "OU=AsiaPacific,OU=Sales,OU=UserAccounts,DC=FABRIKAM,DC=COM" -Country "AU" -StreetAddress "45 Martens Place" -City Balmoral -State QLD -PostalCode 4171 -Replace @{co="Australia"}
```

This command sets the **Country**, **City**, **State**, **PostalCode**, and **Country** properties on the OU OU=AsiaPacific,OU=Sales,OU=UserAccounts,DC=FABRIKAM,DC=COM.

### Example 4: Set a property for an OU in an AD LDS instance
```
PS C:\> Set-ADOrganizationalUnit -Identity "OU=Managed,DC=AppNC" -Server "FABRIKAM-SRV1:60000" -Country "UK"
```

This command sets the **Country** property of the OU OU=Managed,DC=AppNC in an AD LDS instance.

### Example 5: Set a property for a piped OU
```
PS C:\> Get-ADOrganizationalUnit -Identity "AccountingDepartment" | Set-ADOrganizationalUnit -ManagedBy "PattiFullerGroup"
```

This command modifies the **ManagedBy** property for the AccountingDepartment OU.
The command uses the **Get-ADOrganizationalUnit** cmdlet to get the AccountingDepartment OU, and then passes the object to the current cmdlet by using the pipeline operator.

### Example 6: Set a property for a local OU to modify an Active Directory OU
```
PS C:\> $OrganizationalUnit = Get-ADOrganizationalUnit -Identity "AccountingDepartment"
PS C:\> $OrganizationalUnit.ManagedBy = "PattiFullerGroup"
PS C:\> Set-ADOrganizationalUnit -Instance $OrganizationalUnit
```

This example modifies the **ManagedBy** property for the AccountingDepartment OU.
The example modifies a local instance of the AccountingDepartment OU and then specifies the *Instance* parameter for the **Set-ADOrganizationalUnit** cmdlet as the local instance.

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

### -City
Specifies the town or city.
This parameter sets the **City** property of an OU object.
The LDAP display name (**ldapDisplayName**) of this property is l.

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
Specifies the country or region code.
This parameter sets the **Country** property of an OU object.
The LDAP display name (**ldapDisplayName**) of this property is c.
This value is not used by Windows 2000.

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
This parameter sets the value of the **Description** property for the OU object.
The LDAP display name (**ldapDisplayName**) for this property is description.

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
This parameter sets the **DisplayName** property of the OU object.
The LDAP display name (**ldapDisplayName**) for this property is displayName.

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

- A distinguished name
- A GUID (objectGUID)

The cmdlet searches the default naming context or partition to find the object.
If two or more objects are found, the cmdlet returns a non-terminating error.

This parameter can also get this object through the pipeline or you can set this parameter to an object instance.

Derived types, such as the following are also accepted:

- **Microsoft.ActiveDirectory.Management.ADGroup**
- **Microsoft.ActiveDirectory.Management.ADUser**
- **Microsoft.ActiveDirectory.Management.ADComputer**
- **Microsoft.ActiveDirectory.Management.ADServiceAccount**
- **Microsoft.ActiveDirectory.Management.ADFineGrainedPasswordPolicy**
- **Microsoft.ActiveDirectory.Management.ADDomain**

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
Specifies a modified copy of an OU object to use to update the actual Active Directory OU object.
When this parameter is used, any modifications made to the modified copy of the object are also made to the corresponding Active Directory object.
The cmdlet only updates the object properties that have changed.

The *Instance* parameter can only update organizational unit objects that have been retrieved by using the **Get-ADOrganizationalUnit** cmdlet.
When you specify the *Instance* parameter, you cannot specify other parameters that set properties on the object.

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
The acceptable values for this parameter are:

- A distinguished name
- A GUID (objectGUID)
- A security identifier (objectSid)
- A SAM account name (sAMAccountName)

This parameter sets the Active Directory attribute with an LDAP display name of managedBy.

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
The cmdlet searches this partition to find the object defined by the *Identity* parameter.

In many cases, a default value is used for the *Partition* parameter if no value is specified.
The rules for determining the default value are given below.
Note that rules listed first are evaluated first and when a default value can be determined, no further rules are evaluated.

In AD DS environments, a default value for *Partition* are set in the following cases:

- If the *Identity* parameter is set to a distinguished name, the default value of *Partition* is automatically generated from this distinguished name.
- If running cmdlets from an Active Directory provider drive, the default value of *Partition* is automatically generated from the current path in the drive.
- If none of the previous cases apply, the default value of *Partition* is set to the default partition or naming context of the target domain.

In AD LDS environments, a default value for *Partition* will be set in the following cases:

- If the *Identity* parameter is set to a distinguished name, the default value of *Partition* is automatically generated from this distinguished name.
- If running cmdlets from an Active Directory provider drive, the default value of *Partition* is automatically generated from the current path in the drive.
- If the target AD LDS instance has a default naming context, the default value of *Partition* is set to the default naming context.
To specify a default naming context for an AD LDS environment, set the **msDS-defaultNamingContext** property of the Active Directory directory service agent object (**nTDSDSA**) for the AD LDS instance.
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

### -PostalCode
Specifies the postal code or zip code.
This parameter sets the **PostalCode** property of an OU object.
The LDAP display name (**ldapDisplayName**) of this property is postalCode.

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
When this property is set to $True, you cannot delete the corresponding object without changing the value of the property.
The acceptable values for this parameter are:

- $False or 0
- $True or 1

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

When you use the *Add*, *Remove*, *Replace*, and *Clear* parameters together, the operations are performed in the following order:

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
Specifies the state or province.
This parameter sets the **State** property of an OU object.
The LDAP display name (**ldapDisplayName**) of this property is st.

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
Specifies the street address.
This parameter sets the **StreetAddress** property of an OU object.
The LDAP display name (**ldapDisplayName**) of this property is street.

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
An OU object is received by the *Identity* parameter.

An organizational unit object that was retrieved by using the **Get-ADOrganizationalUnit** cmdlet and then modified is received by the *Instance* parameter.

## OUTPUTS

### None or Microsoft.ActiveDirectory.Management.ADOrganizationalUnit
Returns the modified OU object when the *PassThru* parameter is specified.
By default, this cmdlet does not generate any output.

## NOTES
* This cmdlet does not work with an Active Directory snapshot.
* This cmdlet does not work with a read-only domain controller.

## RELATED LINKS

[Get-ADOrganizationalUnit](./Get-ADOrganizationalUnit.md)

[New-ADOrganizationalUnit](./New-ADOrganizationalUnit.md)

[Remove-ADOrganizationalUnit](./Remove-ADOrganizationalUnit.md)

