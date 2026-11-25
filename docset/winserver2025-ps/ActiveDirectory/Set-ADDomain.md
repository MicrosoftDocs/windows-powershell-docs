---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.ActiveDirectory.Management.dll-Help.xml
Module Name: ActiveDirectory
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/activedirectory/set-addomain?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-ADDomain
---

# Set-ADDomain

## SYNOPSIS
Modifies an Active Directory domain.

## SYNTAX

### Identity
```
Set-ADDomain [-WhatIf] [-Confirm] [-Add <Hashtable>] [-AllowedDNSSuffixes <Hashtable>] [-AuthType <ADAuthType>]
 [-Clear <String[]>] [-Credential <PSCredential>] [-Identity] <ADDomain>
 [-LastLogonReplicationInterval <TimeSpan>] [-ManagedBy <ADPrincipal>] [-PassThru]
 [-PublicKeyRequiredPasswordRolling <Boolean>] [-Remove <Hashtable>] [-Replace <Hashtable>] [-Server <String>]
 [<CommonParameters>]
```

### Instance
```
Set-ADDomain [-WhatIf] [-Confirm] [-AllowedDNSSuffixes <Hashtable>] [-AuthType <ADAuthType>]
 [-Credential <PSCredential>] -Instance <ADDomain> [-LastLogonReplicationInterval <TimeSpan>]
 [-ManagedBy <ADPrincipal>] [-PassThru] [-PublicKeyRequiredPasswordRolling <Boolean>] [-Server <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-ADDomain** cmdlet modifies the properties of an Active Directory domain.
You can modify commonly used property values by using the cmdlet parameters.
Property values that are not associated with cmdlet parameters can be modified by using the *Add*, *Replace*, *Clear*, and *Remove* parameters.

The *Identity* parameter specifies the domain to modify.
You can identify a domain by its distinguished name, GUID, security identifier (SID), DNS domain name, or NetBIOS name.
You can also set the *Identity* parameter to an object variable such as `$<localDomainObject>`, or you can pass an object through the pipeline to the *Identity* parameter.
For example, you can use the Get-ADDomain cmdlet to retrieve a domain object and then pass the object through the pipeline to the **Set-ADDomain** cmdlet.

The *Instance* parameter provides a way to update a domain object by applying the changes made to a copy of the domain object.
When you set the *Instance* parameter to a copy of an Active Directory domain object that has been modified, the **Set-ADDomain** cmdlet makes the same changes to the original domain object.
To get a copy of the object to modify, use the Get-ADDomain object.
When you specify the *Instance* parameter you should not pass the *Identity* parameter.
For more information about the *Instance* parameter, see the *Instance* parameter description.

## EXAMPLES

### Example 1: Set the value of a property in a domain
```
PS C:\> Set-ADDomain -Identity USER01 -AllowedDNSSuffixes @{Replace="USER01.com","corp.USER01.com"}
```

This command sets the value of **AllowedDNSSuffixes** to {"USER01.com","corp.USER01.com"} in domain USER01.

### Example 2: Set the value of a property in a domain
```
PS C:\> Set-ADDomain -Identity USER01 -AllowedDNSSuffixes @{Add="corp.USER01.com"}
```

This command adds the value corp.USER01.com to the **AllowedDNSSuffixes** in domain USER01.

### Example 3: Set the ManagedBy property in a domain
```
PS C:\> Set-ADDomain -Identity USER01 -ManagedBy 'CN=Domain Admins,CN=Users,DC=USER01,DC=COM'
```

This command sets the **ManagedBy** property in domain USER01 to CN=Domain Admins,CN=Users,DC=USER01,DC=COM.

### Example 4: Set the time in days for replication for the current logged on user
```
PS C:\> Get-ADDomain | Set-ADDomain -LastLogonReplicationInterval "10"
```

This command sets the **LastLogonReplicationInterval** of the current logged on user domain to 10.

### Example 5: Set the ManagedBy property for a domain
```
PS C:\> $Domain = Get-ADDomain -Identity London
PS C:\> $Domain.ManagedBy = PattiFuller
PS C:\> Set-ADDomain -Instance $Domain
```

This command modifies the **ManagedBy** property for the London domain.
The example modifies a local instance of the London domain, and then specifies the *Instance* parameter for the current cmdlet as the local instance.

### Example 6: Enable password expiration and rolling for public key to sign in
```
PS C:\> Set-ADDomain -Identity FABRIKAM -PublicKeyRequiredPasswordRolling $True
```

This command sets the **msDS-ExpirePasswordsOnSmartCardOnlyAccounts** attribute for the FABRIKAM domain to $True.
This setting enables password expiration and rolling for user accounts that require a public key to sign in.

## PARAMETERS

### -Add
Specifies values to add to an object property.
Use this parameter to add one or more values to a property that cannot be modified using a cmdlet parameter.
To modify an object property, you must use the Lightweight Directory Access Protocol (LDAP) display name.
You can specify multiple values to a property by specifying a comma-separated list of values and more than one property by separating them using a semicolon.
The format for this parameter is

`-Add @{Attribute1LDAPDisplayName=value1, value2, ...;   Attribute2LDAPDisplayName=value1, value2, ...; AttributeNLDAPDisplayName=value1, value2, ...}`

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

### -AllowedDNSSuffixes
Modifies the list of domain name server (DNS) suffixes that are allowed in a domain.
This parameter sets the value of the **msDS-AllowedDNSSuffixes** attribute of the **domainDNS** object.
This parameter uses the following syntax to add, remove, replace, or clear DNS suffix values.

To add values:

`-AllowedDNSSuffixes @{Add=value1,value2,...}`

To remove values:

``-AllowedDNSSuffixes @{Remove=value3,value4,...}

To replace values:

`-AllowedDNSSuffixes @{Replace=value1,value2,...}`

To clear all values:

`-AllowedDNSSuffixes $Null`

You can specify more than one change by using a list separated by semicolons.
For example, use the following syntax to add and remove DNS suffix values:

`@{Add=value1,value2,...};@{Remove=value3,value4,...}`

When you use the *Add*, *Replace*, *Clear*, and *Remove* parameters together, the operations are performed in the following order:

- **Remove**
- **Add**
- **Replace**
- **Clear**

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

### -Identity
Specifies an Active Directory domain object by providing one of the following property values.
The identifier in parentheses is the LDAP display name for the attribute.
All values are for the **domainDNS** object that represents the domain.
The acceptable values for this parameter are:

- A distinguished name
- A GUID (objectGUID)
- A security identifier (objectSid)
- A DNS domain name
- A NetBIOS domain name

The cmdlet searches the default naming context or partition to find the object.
If two or more objects are found, the cmdlet returns a non-terminating error.

This parameter can also get this object through the pipeline or you can set this parameter to a domain object instance.

```yaml
Type: ADDomain
Parameter Sets: Identity
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Instance
Specifies a modified copy of a domain object to use to update the actual Active Directory domain object.
When this parameter is used, any modifications made to the modified copy of the object are also made to the corresponding Active Directory object.
The cmdlet only updates the object properties that have changed.

The *Instance* parameter can only update domain objects that have been retrieved by using the Get-ADDomain cmdlet.
When you specify the *Instance* parameter, you cannot specify other parameters that set properties on the object.

```yaml
Type: ADDomain
Parameter Sets: Instance
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LastLogonReplicationInterval
Specifies the time, in days, within which the last logon time of an account must be replicated across all domain controllers in the domain.
This parameter sets the **LastLogonReplicationInterval** property for a domain.
The LDAP display name (**ldapDisplayName**) for this property is **msDS-LogonTimeSyncInterval**.
The last logon replication interval must be at least one day.
Setting the last logon replication interval to a low value can significantly increase domain-wide replication.

```yaml
Type: TimeSpan
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

This parameter sets the Active Directory attribute with an LDAP display name of managedBy.

```yaml
Type: ADPrincipal
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

### -PublicKeyRequiredPasswordRolling
Specifies whether the domain enables password expiration and rolling for user account that require a smart card for interactive sign in.

```yaml
Type: Boolean
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
The format for this parameter is:

`-Remove @{Attribute1LDAPDisplayName=value[];   Attribute2LDAPDisplayName=value[]}`

When you use the *Add*, *Replace*, *Clear*, and *Remove* parameters together, the operations will be performed in the following order:

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

### None or Microsoft.ActiveDirectory.Management.ADDomain
A domain object is received by the *Identity* parameter.

A domain object that was retrieved by using the Get-ADDomain cmdlet and then modified is received by the *Instance* parameter.

## OUTPUTS

### None or Microsoft.ActiveDirectory.Management.ADDomain
This cmdlet returns the modified domain object when the *PassThru* parameter is specified.
By default, this cmdlet does not generate any output.

## NOTES
* This cmdlet does not work with Active Directory Lightweight Directory Services (AD LDS).
* This cmdlet does not work with an Active Directory snapshot.
* This cmdlet does not work with a read-only domain controller.

## RELATED LINKS

[Get-ADDomain](./Get-ADDomain.md)

[Get-ADDomainController](./Get-ADDomainController.md)

