---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.ActiveDirectory.Management.dll-Help.xml
Module Name: ActiveDirectory
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/activedirectory/set-adserviceaccount?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-ADServiceAccount
---

# Set-ADServiceAccount

## SYNOPSIS
Modifies an Active Directory managed service account or group managed service account object.

## SYNTAX

### Identity
```
Set-ADServiceAccount [-WhatIf] [-Confirm] [-AccountExpirationDate <DateTime>] [-AccountNotDelegated <Boolean>]
 [-Add <Hashtable>] [-AuthenticationPolicy <ADAuthenticationPolicy>]
 [-AuthenticationPolicySilo <ADAuthenticationPolicySilo>] [-AuthType <ADAuthType>] [-Certificates <String[]>]
 [-Clear <String[]>] [-CompoundIdentitySupported <Boolean>] [-Credential <PSCredential>]
 [-Description <String>] [-DisplayName <String>] [-DNSHostName <String>] [-Enabled <Boolean>]
 [-HomePage <String>] [-Identity] <ADServiceAccount> [-KerberosEncryptionType <ADKerberosEncryptionType>]
 [-Partition <String>] [-PassThru] [-PrincipalsAllowedToDelegateToAccount <ADPrincipal[]>]
 [-PrincipalsAllowedToRetrieveManagedPassword <ADPrincipal[]>] [-Remove <Hashtable>] [-Replace <Hashtable>]
 [-SamAccountName <String>] [-Server <String>] [-ServicePrincipalNames <Hashtable>]
 [-TrustedForDelegation <Boolean>] [<CommonParameters>]
```

### Instance
```
Set-ADServiceAccount [-WhatIf] [-Confirm] [-AuthType <ADAuthType>] [-Credential <PSCredential>]
 -Instance <ADServiceAccount> [-PassThru] [-Server <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-ADServiceAccount** cmdlet modifies the properties of an Active Directory managed service account (MSA).
You can modify commonly used property values by using the cmdlet parameters.
Property values that are not associated with cmdlet parameters can be modified by using the *Add*, *Remove*, *Replace*, and *Clear* parameters.

The *Identity* parameter specifies the Active Directory MSA to modify.
You can identify an MSA by its distinguished name, GUID, security identifier (SID), or Security Account Manager (SAM) account name.
You can also set the *Identity* parameter to an object variable such as `$<localServiceAccountObject>`, or you can pass an object through the pipeline to the *Identity* parameter.
For example, you can use the **Get-ADServiceAccount** cmdlet to retrieve a MSA object and then pass the object through the pipeline to the **Set-ADServiceAccount** cmdlet.

The *Instance* parameter provides a way to update an MSA object by applying the changes made to a copy of the object.
When you set the *Instance* parameter to a copy of an Active Directory MSA object that has been modified, the **Set-ADServiceAccount** cmdlet makes the same changes to the original MSA object.
To get a copy of the object to modify, use the **Get-ADServiceAccount** object.
When you specify the *Instance* parameter you should not pass the *Identity* parameter.
For more information about the *Instance* parameter, see the *Instance* parameter description.

## EXAMPLES

### Example 1: Set the description for an MSA
```
PS C:\> Set-ADServiceAccount -Identity Service1 -Description "Secretive Data Server"
```

This command sets the description of the MSA identified as Service1 to Secretive Data Server.

### Example 2: Replace the value of a property for an MSA
```
PS C:\> Set-ADServiceAccount -Identity Mongol01ADAM -ServicePrincipalNames @{replace="ADAMwdb/a.contoso.com", "ADAMbdb/a.contoso.com"}
```

This command replaces the value of property **ServicePrincipalNames** with ADAMwdb/a.contoso.com, ADAMbdb/a.contoso.com.

### Example 3: Set the principals allowed to retrieve the password for an MSA
```
PS C:\> Set-ADServiceAccount -Identity Service1 -PrincipalsAllowedToRetrieveManagedPassword "MsaAdmins.corp.contoso.com"
```

This command sets the principals allowed to retrieve the password for this MSA to be limited to members of the specified Active Directory group account.

### Example 4: Set the ServicePrincipalNames property
```
PS C:\> Set-ADServiceAccount -Identity AccessTSQA -ServicePrincipalNames @{Add=ACCESSAPP/TSQA.contoso.com}
```

This command modifies the **ServicePrincipalNames** property for the AccessTSQA MSA by specifying the *Identity* and *ServicePrincipalNames* parameters.

### Example 5: Get a specified MSA and modify its ServicePrincipalNames property
```
PS C:\> Get-ADServiceAccount -Identity "AccessTSQA" | Set-ADServiceAccount -ServicePrincipalNames @{Add=ACCESSAPP/TSQA.contoso.com}
```

This command modifies the **ServicePrincipalNames** property for the AccessTSQA MSA.
The command uses the **Get-ADServiceAccount** cmdlet to get the AccessTSQA MSA, and then passes the AccessTSQA MSA to the current cmdlet by using the pipeline operator.

### Example 6: Set an MSA from a local instance
```
PS C:\> $ServiceAccount = Get-ADServiceAccount -Identity "AccessTSQA"
PS C:\> $ServiceAccount.ServicePrincipalNames = @{Add=ACCESSAPP/TSQA.contoso.com}
PS C:\> Set-ADServiceAccount -Instance $ServiceAccount
```

This example modifies the **ServicePrincipalNames** property for the AccessTSQA MSA.
The example modifies a local instance of the AccessTSQA MSA, and then specifies the *Instance* parameter for the current cmdlet as the local instance.

## PARAMETERS

### -AccountExpirationDate
Specifies the expiration date for an account.
This parameter sets the **AccountExpirationDate** property of an account object.
The Lightweight Directory Access Protocol (LDAP) display name (**ldapDisplayName**) for this property is accountExpires.

Use the **DateTime** syntax when you specify this parameter.
Time is assumed to be local time unless otherwise specified.
When a time value is not specified, the time is assumed to 12:00:00 AM local time.
When a date is not specified, the date is assumed to be the current date.

```yaml
Type: DateTime
Parameter Sets: Identity
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AccountNotDelegated
Indicates whether the security context of the user is delegated to a service.
When this parameter is set to true, the security context of the account is not delegated to a service even when the service account is set as trusted for Kerberos delegation.
This parameter sets the **AccountNotDelegated** property for an Active Directory account.
This parameter also sets the **ADS_UF_NOT_DELEGATED** flag of the Active Directory User Account Control (UAC) attribute.

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

### -Add
Specifies values to add to an object property.
Use this parameter to add one or more values to a property that cannot be modified using a cmdlet parameter.
To modify an object property, you must use the LDAP display name.
You can specify multiple values to a property by specifying a comma-separated list of values and more than one property by separating them using a semicolon.
The format for this parameter is:

`-Add @{Attribute1LDAPDisplayName=value1, value2, ...;   Attribute2LDAPDisplayName=value1, value2, ...; AttributeNLDAPDisplayName=value1, value2, ...}`

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


### -AuthenticationPolicy
Specifies an Active Directory Domain Services (AD DS) authentication policy object.
Specify the authentication policy object in one of the following formats:

- Distinguished name
- GUID
- Name

This parameter can also get this object through the pipeline or you can set this parameter to an object instance.

The cmdlet searches the default naming context or partition to find the object.
If the cmdlet finds two or more objects, the cmdlet returns a non-terminating error.

```yaml
Type: ADAuthenticationPolicy
Parameter Sets: Identity
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AuthenticationPolicySilo
Specifies an AD DS authentication policy silo object.
Specify the authentication policy silo object in one of the following formats:

- Distinguished name
- GUID
- Name

This parameter can also get this object through the pipeline or you can set this parameter to an object instance.

The cmdlet searches the default naming context or partition to find the object.
If the cmdlet finds two or more objects, the cmdlet returns a non-terminating error.

```yaml
Type: ADAuthenticationPolicySilo
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

### -Certificates
Specifies an array of certificates.
The cmdlet modifies the DER-encoded X.509v3 certificates of the account.
These certificates include the public key certificates issued to this account by the Microsoft Certificate Service.
This parameter sets the **Certificates** property of the account object.
The Lightweight Directory Access Protocol (LDAP) display name (**ldapDisplayName**) for this property is userCertificate.

To add values:

`-Certificates @{Add=value1,value2,...}`

To remove values:

`-Certificates @{Remove=value3,value4,...}`

To replace values:

`-Certificates @{Replace=value1,value2,...}`

To clear all values:

`-Certificates $Null`

You can specify more than one operation by using a list separated by semicolons.
For example, use the following syntax to add and remove **Certificates** values:

`-Certificates @{Add=value1,value2,...};@{Remove=value3,value4,...}`

The operators are applied in the following sequence:

- Remove
- Add
- Replace

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

### -CompoundIdentitySupported
Indicates whether an account supports Kerberos service tickets which includes the authorization data for the user's device.
This value sets the compound identity supported flag of the Active Directory **msDS-SupportedEncryptionTypes** attribute.

Warning: Domain-joined Windows systems and services such as clustering manage their own **msDS-SupportedEncryptionTypes** attribute.
Therefore any changes to the flag on the **msDS-SupportedEncryptionTypes** attribute will be overwritten by the service or system which manages the setting.

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

### -DNSHostName
Specifies the DNS host name.

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

### -Enabled
Specifies if an account is enabled.
An enabled account requires a password.
This parameter sets the **Enabled** property for an account object.
This parameter also sets the **ADS_UF_ACCOUNTDISABLE** flag of the Active Directory User Account Control (UAC) attribute.

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

### -HomePage
Specifies the URL of the home page of the object.
This parameter sets the **homePage** property of an Active Directory object.
The LDAP display name (**ldapDisplayName**) for this property is wWWHomePage.

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
Specifies an Active Directory account object by providing one of the following property values.
The identifier in parentheses is the LDAP display name for the attribute.
The acceptable values for this parameter are:

- A distinguished name
- A GUID (objectGUID)
- A security identifier (objectSid)
- A SAM account name (sAMAccountName)

The cmdlet searches the default naming context or partition to find the object.
If two or more objects are found, the cmdlet returns a non-terminating error.

This parameter can also get this object through the pipeline or you can set this parameter to an object instance.

```yaml
Type: ADServiceAccount
Parameter Sets: Identity
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Instance
Specifies a modified copy of a service account object to use to update the actual Active Directory service account object.
When this parameter is used, any modifications made to the modified copy of the object are also made to the corresponding Active Directory object.
The cmdlet only updates the object properties that have changed.

The *Instance* parameter can only update service account objects that have been retrieved by using the **Get-ADServiceAccount** cmdlet.
When you specify the *Instance* parameter, you cannot specify other parameters that set properties on the object.

```yaml
Type: ADServiceAccount
Parameter Sets: Instance
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -KerberosEncryptionType
Specifies whether an account supports Kerberos encryption types that are used when creating service tickets.
This value sets the encryption types supported flags of the Active Directory **msDS-SupportedEncryptionTypes** attribute.
The acceptable values for this parameter are:

- None
- DES
- RC4
- AES128
- AES256

None removes all encryption types from the account, which may result in the KDC being unable to issue service tickets for services using the account.

DES is a weak encryption type that is not supported by default since Windows 7 and Windows Server 2008 R2.

Warning: Domain-joined Windows systems and services such as clustering manage their own **msDS-SupportedEncryptionTypes** attribute.
Therefore any changes to the flag on the **msDS-SupportedEncryptionTypes** attribute are overwritten by the service or system that manages the setting.

```yaml
Type: ADKerberosEncryptionType
Parameter Sets: Identity
Aliases:
Accepted values: None, DES, RC4, AES128, AES256

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
Note that rules listed first are evaluated first and once a default value can be determined, no further rules are evaluated.

In Active Directory Domain Services (AD DS) environments, a default value for *Partition* is set in the following cases:

- If the *Identity* parameter is set to a distinguished name, the default value of *Partition* is automatically generated from this distinguished name.
- If running cmdlets from an Active Directory provider drive, the default value of *Partition* is automatically generated from the current path in the drive.
- If none of the previous cases apply, the default value of *Partition* is set to the default partition or naming context of the target domain.

In AD LDS environments, a default value for *Partition* is set in the following cases:

- If the *Identity* parameter is set to a distinguished name, the default value of *Partition* is automatically generated from this distinguished name.
- If running cmdlets from an Active Directory provider drive, the default value of *Partition* is automatically generated from the current path in the drive.
- If the target AD LDS instance has a default naming context, the default value of *Partition* will be set to the default naming context.
To specify a default naming context for an AD LDS environment, set the **msDS-defaultNamingContext** property of the Active Directory directory service agent (DSA) object (**nTDSDSA**) for the AD LDS instance.
- If none of the previous cases apply, the *Partition* parameter will not take any default value.

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

### -PrincipalsAllowedToDelegateToAccount
Specifies the accounts which can act on the behalf of users to services running as this Managed Service Account or Group Managed Service Account.
This parameter sets the **msDS-AllowedToActOnBehalfOfOtherIdentity** attribute of the object.

```yaml
Type: ADPrincipal[]
Parameter Sets: Identity
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PrincipalsAllowedToRetrieveManagedPassword
Specifies the membership policy for systems which can use a group managed service account.
For a service to run under a group managed service account, the system must be in the membership policy of the account.
This parameter sets the **msDS-GroupMSAMembership** attribute of a group managed service account object.
This parameter should be set to the principals allowed to use this group managed service account.

```yaml
Type: ADPrincipal[]
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

When you use the *Add*, *Remove*, *Replace*, and *Clear* parameters together, the parameters will be applied in the following sequence:

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

### -SamAccountName
Specifies the Security Account Manager (SAM) account name of the user, group, computer, or service account.
The maximum length of the description is 256 characters.
To be compatible with older operating systems, create a SAM account name that is 20 characters or less.
This parameter sets the **SAMAccountName** for an account object.
The LDAP display name (**ldapDisplayName**) for this property is sAMAccountName.

Note: If the string value provided is not terminated with a $ character, the system adds one if needed.

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
The service may be any of the following: Active Directory Lightweight Domain Services, Active Directory Domain Services or Active Directory Snapshot instance.

Domain name values:

- Fully qualified domain name (FQDN)
- NetBIOS name

Directory server values:

- Fully qualified directory server name
- NetBIOS name
- Fully qualified directory server name and port

The default value for the *Server* parameter is determined by one of the following methods in the order that they are listed:

- By using *Server* value from objects passed through the pipeline.
- By using the server information associated with the Active Directory PowerShell provider drive, when running under that drive.
- By using the domain of the computer running PowerShell.

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

### -ServicePrincipalNames
Specifies the service principal names for the account.
This parameter sets the **ServicePrincipalNames** property of the account.
The LDAP display name (**ldapDisplayName**) for this property is servicePrincipalName.
This parameter uses the following syntax to add, remove, replace, or clear service principal name values.

To add values:

`-ServicePrincipalNames @{Add=value1,value2,...}`

To remove values:

`-ServicePrincipalNames @{Remove=value3,value4,...}`

To replace values:

`-ServicePrincipalNames @{Replace=value1,value2,...}`

To clear all values:

`-ServicePrincipalNames $Null`

You can specify more than one change by using a list separated by semicolons.
For example, use the following syntax to add and remove service principal names.

`@{Add=value1,value2,...};@{Remove=value3,value4,...}`

The operators are applied in the following sequence:

- Remove
- Add
- Replace

The following example shows how to add and remove service principal names:

```powershell
 -ServicePrincipalNames @{Add="SQLservice\accounting.corp.contoso.com:1456"};{Remove="SQLservice\finance.corp.contoso.com:1456"}
```

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

### -TrustedForDelegation
Indicates whether an account is trusted for Kerberos delegation.
A service that runs under an account that is trusted for Kerberos delegation can assume the identity of a client requesting the service.
This parameter sets the **TrustedForDelegation** property of an account object.
This value also sets the **ADS_UF_TRUSTED_FOR_DELEGATION** flag of the Active Directory User Account Control attribute.
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

### None or Microsoft.ActiveDirectory.Management.ADServiceAccount
A managed service account object is received by the *Identity* parameter.

A managed service account object that was retrieved by using the **Get-ADServiceAccount** cmdlet and then modified is received by the *Instance* parameter.

## OUTPUTS

### None or Microsoft.ActiveDirectory.Management.ADServiceAccount
Returns the modified managed service account object when the *PassThru* parameter is specified.
By default, this cmdlet does not generate any output.

## NOTES
* This cmdlet does not work with AD LDS.
* This cmdlet does not work with an Active Directory snapshot.
* This cmdlet does not work with a read-only domain controller.

## RELATED LINKS

[Get-ADServiceAccount](./Get-ADServiceAccount.md)

[Install-ADServiceAccount](./Install-ADServiceAccount.md)

[New-ADServiceAccount](./New-ADServiceAccount.md)

[Remove-ADServiceAccount](./Remove-ADServiceAccount.md)

[Uninstall-ADServiceAccount](./Uninstall-ADServiceAccount.md)

