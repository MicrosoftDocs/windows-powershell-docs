---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.ActiveDirectory.Management.dll-Help.xml
Module Name: ActiveDirectory
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/activedirectory/set-adfinegrainedpasswordpolicy?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-ADFineGrainedPasswordPolicy
---

# Set-ADFineGrainedPasswordPolicy

## SYNOPSIS
Modifies an Active Directory fine-grained password policy.

## SYNTAX

### Identity
```
Set-ADFineGrainedPasswordPolicy [-WhatIf] [-Confirm] [-Add <Hashtable>] [-AuthType <ADAuthType>]
 [-Clear <String[]>] [-ComplexityEnabled <Boolean>] [-Credential <PSCredential>] [-Description <String>]
 [-DisplayName <String>] [-Identity] <ADFineGrainedPasswordPolicy> [-LockoutDuration <TimeSpan>]
 [-LockoutObservationWindow <TimeSpan>] [-LockoutThreshold <Int32>] [-MaxPasswordAge <TimeSpan>]
 [-MinPasswordAge <TimeSpan>] [-MinPasswordLength <Int32>] [-PassThru] [-PasswordHistoryCount <Int32>]
 [-Precedence <Int32>] [-ProtectedFromAccidentalDeletion <Boolean>] [-Remove <Hashtable>]
 [-Replace <Hashtable>] [-ReversibleEncryptionEnabled <Boolean>] [-Server <String>] [<CommonParameters>]
```

### Instance
```
Set-ADFineGrainedPasswordPolicy [-WhatIf] [-Confirm] [-AuthType <ADAuthType>] [-Credential <PSCredential>]
 -Instance <ADFineGrainedPasswordPolicy> [-PassThru] [-Server <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-ADFineGrainedPasswordPolicy** cmdlet modifies the properties of an Active Directory fine-grained password policy.
You can modify commonly used property values by using the cmdlet parameters.
Property values that are not associated with cmdlet parameters can be modified by using the *Add*, *Replace*, *Clear*, and *Remove* parameters.

The *Identity* parameter specifies the Active Directory fine-grained password policy to modify.
You can identify a fine-grained password policy by its distinguished name, GUID or name.
You can also set the *Identity* parameter to an object variable such as `$<localFineGrainedPasswordPolicyObject>`, or you can pass an object through the pipeline to the *Identity* parameter.
For example, you can use the **Get-ADFineGrainedPasswordPolicy** cmdlet to retrieve a fine-grained password policy object and then pass the object through the pipeline operator to the **Set-ADFineGrainedPasswordPolicy** cmdlet.

The *Instance* parameter provides a way to update a fine-grained password policy object by applying the changes made to a copy of the object.
When you set the *Instance* parameter to a copy of an Active Directory fine-grained password policy object that has been modified, the **Set-ADFineGrainedPasswordPolicy** cmdlet makes the same changes to the original fine-grained password policy object.
To get a copy of the object to modify, use the Get-ADFineGrainedPasswordPolicy object.
The *Identity* parameter is not allowed when you use the *Instance* parameter.
For more information about the *Instance* parameter, see the *Instance* parameter description.

## EXAMPLES

### Example 1: Update properties on a fine-grained password policy object
```
PS C:\> Set-ADFineGrainedPasswordPolicy -Identity MyPolicy -Precedence 100 -LockoutDuration 00:40:00 -LockoutObservationWindow 00:20:00 -ComplexityEnabled $True -ReversibleEncryptionEnabled $false -MinPasswordLength 12
```

This command updates the **Precedence**, **LockoutDuration**, **LockoutObservationWindow**, **ComplexityEnabled**, **ReversibleEncryptionEnabled**, and **MinPasswordLength** properties on the **FineGrainedPasswordPolicy** object with name MyPolicy.

### Example 2: Set a property on a fine-grained password policy using distinguished name
```
PS C:\> Set-ADFineGrainedPasswordPolicy -Identity 'CN=MyPolicy,CN=Password Settings Container,CN=System,DC=FABRIKAM,DC=COM' -MinPasswordLength 12
```

This command sets the **MinPasswordLength** property on the **FineGrainedPasswordPolicy** object with distinguished name CN=MyPolicy,CN=Password Settings Container,CN=System,DC=USER01,DC=COM.

### Example 3: Get a fine-grained password policy then update a set of properties
```
PS C:\> $FGPP = Get-ADFineGrainedPasswordPolicy -Identity MyPolicy
PS C:\> $FGPP.LockoutObservationWindow = [TimeSpan]::Parse("0.00:15:00")
PS C:\> $FGPP.LockoutThreshold = 10
PS C:\> $FGPP.MinPasswordLength = 8
PS C:\> $FGPP.PasswordHistoryCount = 24
PS C:\> Set-ADFineGrainedPasswordPolicy -Instance $FGPP
```

This example gets the **FineGrainedPasswordPolicy** object with name MyPolicy, updates a set of properties on the object, and then writes the modifications back to the directory using the *Instance* parameter.

### Example 4: Update a property for a specific fine-grained password policy
```
PS C:\> Get-ADFineGrainedPasswordPolicy -Identity "Level3Policy" | Set-ADFineGrainedPasswordPolicy -Precedence 150
```

This command modifies the **Precedence** property for the fine-grained password policy named Level3Policy.
The command uses the **Get-ADFineGrainedPasswordPolicy** cmdlet to get the fine-grained password policy, and then passes the policy to the current cmdlet by using the pipeline operator.

## PARAMETERS

### -Add
Specifies values to add to an object property.
Use this parameter to add one or more values to a property that cannot be modified using a cmdlet parameter.
To modify an object property, you must use the Lightweight Directory Access Protocol (LDAP) display name.
You can specify multiple values to a property by specifying a comma-separated list of values and more than one property by separating them using a semicolon.
The format for this parameter is:

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

### -ComplexityEnabled
Specifies whether password complexity is enabled for the password policy.
If enabled, the password must contain three of the following four character types:

- Uppercase characters (A, B, C, D, E, ...)
- Lowercase characters (a, b, c, d, e, ...)
- Numerals (0, 1, 2, 3, ...)
- Special characters (#, $, *, %, ...)

This parameter sets the **ComplexityEnabled** property of a password policy.
The acceptable values for this parameter are:

- $False or 0.
Disables password complexity.
- $True or 1.
Enables password complexity.

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

### -Identity
Specifies an Active Directory fine-grained password policy object by providing one of the following property values.
The identifier in parentheses is the LDAP display name for the attribute.
The acceptable values for this parameter are:

- A Distinguished Name (distinguishedName)
- A GUID (objectGUID)
- A Name (name)

The cmdlet searches the default naming context or partition to find the object.
If two or more objects are found, the cmdlet returns a non-terminating error.

This parameter can also get this object through the pipeline operator or you can set this parameter to a fine-grained password policy object instance.

```yaml
Type: ADFineGrainedPasswordPolicy
Parameter Sets: Identity
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Instance
Specifies a modified copy of a fine-grained password policy object to use to update the actual Active Directory fine-grained password policy object.
When this parameter is used, any modifications made to the modified copy of the object are also made to the corresponding Active Directory object.
The cmdlet only updates the object properties that have changed.

The *Instance* parameter can only update fine-grained password policy objects that have been retrieved by using the **Get-ADFineGrainedPasswordPolicy** cmdlet.
When you specify the *Instance* parameter, you cannot specify other parameters that set properties on the object.

```yaml
Type: ADFineGrainedPasswordPolicy
Parameter Sets: Instance
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LockoutDuration
Specifies the length of time that an account is locked after the number of failed login attempts exceeds the lockout threshold.
You cannot login to an account that is locked until the lockout duration time period has expired.
This parameter sets the **lockoutDuration** property of a password policy object.
The LDAP display name (**ldapDisplayName**) of this property is msDS-LockoutDuration.

The lockout duration must be greater than or equal to the lockout observation time for a password policy.
Use the *LockOutObservationWindow* parameter to set the lockout observation time.

Specify the lockout duration time interval in the following format:

D.H:M:S.F

where:

D = Days (0 to 10675199)

H = Hours (0 to 23)

M = Minutes (0 to 59)

S = Seconds (0 to 59)

F= Fractions of a second (0 to 9999999)

```yaml
Type: TimeSpan
Parameter Sets: Identity
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LockoutObservationWindow
Specifies the maximum time interval between two unsuccessful login attempts before the number of unsuccessful login attempts is reset to 0.
An account is locked when the number of unsuccessful login attempts exceeds the password policy lockout threshold.
This parameter sets the **lockoutObservationWindow** property of a password policy object.
The LDAP display name (**ldapDisplayName**) of this property is msDS-lockoutObservationWindow.

The lockout observation window must be smaller than or equal to the lockout duration for a password policy.
Use the *LockoutDuration* parameter to set the lockout duration time.

Specify the time interval in the following format:

D:H:M:S.F

where:

D = Days (0 to 10675199)

H = Hours (0 to 23)

M = Minutes (0 to 59)

S = Seconds (0 to 59)

F= Fractions of a second (0 to 9999999)

Note: Time values must be between the following values: 0:0:0:0.0 and 10675199:02:48:05.4775807.

```yaml
Type: TimeSpan
Parameter Sets: Identity
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LockoutThreshold
Specifies the number of unsuccessful login attempts that are permitted before an account is locked out.
This number increases when the time between unsuccessful login attempts is less than the time specified for the lockout observation time window.
This parameter sets the **LockoutThreshold** property of a password policy.

```yaml
Type: Int32
Parameter Sets: Identity
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaxPasswordAge
Specifies the maximum length of time that you can have the same password.
After this time period, the password expires and you must create a new one.

This parameter sets the **maxPasswordAge** property of a password policy.
The LDAP display name (**ldapDisplayName**) for this property is maxPwdAge.

Specify the time interval in the following format:

D.H:M:S.F

where:

D = Days (0 to 10675199)

H = Hours (0 to 23)

M = Minutes (0 to 59)

S = Seconds (0 to 59)

F= Fractions of a second (0 to 9999999)

Note: Time values must be between the following values: 0:0:0:0.0 and 10675199:02:48:05.4775807.

```yaml
Type: TimeSpan
Parameter Sets: Identity
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MinPasswordAge
Specifies the minimum length of time before you can change a password.

This parameter sets the **minPasswordAge** property of a password policy.
The LDAP display name (**ldapDisplayName**) for this property is minPwdAge.

Specify the time interval in the following format:

D.H:M:S.F

where:

D = Days (0 to 10675199)

H = Hours (0 to 23)

M = Minutes (0 to 59)

S = Seconds (0 to 59)

F= Fractions of a second (0 to 9999999)

Note: Time values must be between the following values:  0:0:0:0.0 and 10675199:02:48:05.4775807.

```yaml
Type: TimeSpan
Parameter Sets: Identity
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MinPasswordLength
Specifies the minimum number of characters that a password must contain.
This parameter sets the **MinPasswordLength** property of the password policy.

```yaml
Type: Int32
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

### -PasswordHistoryCount
Specifies the number of previous passwords to save.
A user cannot reuse a password in the list of saved passwords.
This parameter sets the **PasswordHistoryCount** property for a password policy.

```yaml
Type: Int32
Parameter Sets: Identity
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Precedence
Specifies a value that defines the precedence of a fine-grained password policy among all fine-grained password policies.
This parameter sets the **Precedence** property for a fine-grained password policy.
The LDAP display name (**ldapDisplayName**) for this property is msDS-PasswordSettingsPrecedence.

This value determines which password policy to use when more than one password policy applies to a user or group.
When there is a conflict, the password policy that has the lower **Precedence** property value has higher priority.
For example, if PasswordPolicy1 has a **Precedence** property value of 200 and PasswordPolicy2 has a **Precedence** property value of 100, PasswordPolicy2 is used.

Typically, password policy precedence values are assigned in multiples of 10 or 100, making it easier to add policies at a later time.
For example, if you set the initial precedence values for your policies to 100 and 200, you can add another policy that has precedence value of 150.

If the specified *Precedence* parameter is already assigned to another password policy object, the cmdlet returns a terminating error.

```yaml
Type: Int32
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

### -ReversibleEncryptionEnabled
Specifies whether the directory must store passwords using reversible encryption.
This parameter sets the **ReversibleEncryption** property for a password policy.
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

### -Server
Specifies the Active Directory Domain Services instance to connect to, by providing one of the following values for a corresponding domain name or directory server.
The service may be any of the following: Active Directory Lightweight Domain Services, Active Directory Domain Services, or Active Directory snapshot instance.

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

### None or Microsoft.ActiveDirectory.Management.ADFineGrainedPasswordPolicy
A fine-grained password policy object is received by the *Identity* parameter.

A fine-grained password policy object that was retrieved by using the **Get-ADFineGrainedPasswordPolicy** cmdlet and then modified is received by the *Instance* parameter.

## OUTPUTS

### None or Microsoft.ActiveDirectory.Management.ADFineGrainedPasswordPolicy
This cmdlet returns the modified fine-grained password policy object when the *PassThru* parameter is specified.
By default, this cmdlet does not generate any output.

## NOTES
* This cmdlet does not work with Active Directory Lightweight Directory Services (AD LDS).
* This cmdlet does not work with an Active Directory snapshot.
* This cmdlet does not work with a read-only domain controller.

## RELATED LINKS

[Get-ADFineGrainedPasswordPolicy](./Get-ADFineGrainedPasswordPolicy.md)

[New-ADFineGrainedPasswordPolicy](./New-ADFineGrainedPasswordPolicy.md)

[Remove-ADFineGrainedPasswordPolicy](./Remove-ADFineGrainedPasswordPolicy.md)

[AD DS Administration Cmdlets in Windows PowerShell](./activedirectory.md)

