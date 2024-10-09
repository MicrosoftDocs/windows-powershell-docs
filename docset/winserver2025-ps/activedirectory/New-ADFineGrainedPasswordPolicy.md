---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.ActiveDirectory.Management.dll-Help.xml
Module Name: ActiveDirectory
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/activedirectory/new-adfinegrainedpasswordpolicy?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-ADFineGrainedPasswordPolicy
---

# New-ADFineGrainedPasswordPolicy

## SYNOPSIS
Creates a new Active Directory fine-grained password policy.

## SYNTAX

```powershell
New-ADFineGrainedPasswordPolicy [-WhatIf] [-Confirm] [-AuthType <ADAuthType>] [-ComplexityEnabled <Boolean>]
 [-Credential <PSCredential>] [-Description <String>] [-DisplayName <String>]
 [-Instance <ADFineGrainedPasswordPolicy>] [-LockoutDuration <TimeSpan>] [-LockoutObservationWindow <TimeSpan>]
 [-LockoutThreshold <Int32>] [-MaxPasswordAge <TimeSpan>] [-MinPasswordAge <TimeSpan>]
 [-MinPasswordLength <Int32>] [-Name] <String> [-OtherAttributes <Hashtable>] [-PassThru]
 [-PasswordHistoryCount <Int32>] [-Precedence] <Int32> [-ProtectedFromAccidentalDeletion <Boolean>]
 [-ReversibleEncryptionEnabled <Boolean>] [-Server <String>] [<CommonParameters>]
```

## DESCRIPTION
The **New-ADFineGrainedPasswordPolicy** cmdlet creates a new Active Directory fine-grained password policy.
You can set commonly used fine-grained password policy property values by using the cmdlet parameters.
Property values that are not associated with cmdlet parameters can be set by using the *OtherAttributes* parameter.

You must set the *Name* and *Precedence* parameters to create a new fine-grained password policy.

The following methods explain different ways to create an object by using this cmdlet.

Method 1: Use the **New-ADFineGrainedPasswordPolicy** cmdlet, specify the required parameters, and set any additional property values by using the cmdlet parameters.

Method 2: Use a template to create the new object.
To do this, create a new fine-grained password policy object or retrieve a copy of an existing fine-grained password policy object and set the *Instance* parameter to this object.
The object provided to the *Instance* parameter is used as a template for the new object.
You can override property values from the template by setting cmdlet parameters.
For examples and more information, see the *Instance* parameter description for this cmdlet.

Method 3: Use the Import-Csv cmdlet with the **New-ADFineGrainedPasswordPolicy** cmdlet to create multiple Active Directory fine-grained password policy objects.
To do this, use the **Import-Csv** cmdlet to create the custom objects from a comma-separated value (CSV) file that contains a list of object properties.
Then pass these objects through the pipeline operator to the **New-ADFineGrainedPasswordPolicy** cmdlet to create the fine-grained password policy objects.

## EXAMPLES

### Example 1: Create a fine-grained password policy
```powershell
PS C:\> New-ADFineGrainedPasswordPolicy -Name "DomainUsersPSO" -Precedence 500 -ComplexityEnabled $true -Description "The Domain Users Password Policy" -DisplayName "Domain Users PSO" -LockoutDuration "0.12:00:00" -LockoutObservationWindow "0.00:15:00" -LockoutThreshold 10
```

This command creates a fine-grained password policy object named DomainUsersPSO and set the **Precedence**, **ComplexityEnabled**, **Description**, **DisplayName**, **LockoutDuration**, **LockoutObservationWindow**, and **LockoutThreshold** properties on the object.

### Example 2: Create fine-grained password policies using a template object
```powershell
PS C:\> $TemplatePSO = New-Object Microsoft.ActiveDirectory.Management.ADFineGrainedPasswordPolicy
PS C:\> $TemplatePSO.ComplexityEnabled = $true
PS C:\> $TemplatePSO.LockoutDuration = [TimeSpan]::Parse("0.12:00:00")
PS C:\> $TemplatePSO.LockoutObservationWindow = [TimeSpan]::Parse("0.00:15:00")
PS C:\> $TemplatePSO.LockoutThreshold = 10
PS C:\> $TemplatePSO.MinPasswordAge = [TimeSpan]::Parse("0.00:10:00")
PS C:\> $TemplatePSO.PasswordHistoryCount = 24
PS C:\> $TemplatePSO.ReversibleEncryptionEnabled = $false
PS C:\> New-ADFineGrainedPasswordPolicy -Instance $TemplatePSO -Name "SvcAccPSO" -Precedence 100 -Description "The Service Accounts Password Policy" -DisplayName "Service Accounts PSO" -MaxPasswordAge "30.00:00:00" -MinPasswordLength 20
PS C:\> New-ADFineGrainedPasswordPolicy -Instance $TemplatePSO -Name "AdminsPSO" -Precedence 200 -Description "The Domain Administrators Password Policy" -DisplayName "Domain Administrators PSO" -MaxPasswordAge "15.00:00:00" -MinPasswordLength 10
```

This example creates two new fine-grained password policy objects using a template object.

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
The Lightweight Directory Access Protocol (LDAP) display name (**ldapDisplayName**) for this property is description.

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
Specifies an instance of a fine-grained password policy object to use as a template for a new fine-grained password policy object.

You can use an instance of an existing fine-grained password policy object as a template or you can construct a new fine-grained password policy object by using the Windows PowerShell command line or by using a script.

Method 1: Use an existing fine-grained password policy object as a template for a new object.
To retrieve an instance of an existing fine-grained password policy object, use a cmdlet such as **Get-ADFineGrainedPasswordPolicy**.
Then provide this object to the *Instance* parameter of the **New-ADFineGrainedPasswordPolicy** cmdlet to create a new fine-grained password policy object.
You can override property values of the new object by setting the appropriate parameters.

Method 2: Create a new **ADFineGrainedPasswordPolicy** object and set the property values by using the Windows PowerShell command line interface.
Then pass this object to the *Instance* parameter of the **New-ADFineGrainedPasswordPolicy** cmdlet to create the new Active Directory fine-grained password policy object.

Note: Specified attributes are not validated, so attempting to set attributes that do not exist or cannot be set will raise an error.

```yaml
Type: ADFineGrainedPasswordPolicy
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LockoutDuration
Specifies the length of time that an account is locked after the number of failed login attempts exceeds the lockout threshold.
You cannot log in to an account that is locked until the lockout duration time period has expired. If you set the value to 0 the account needs to be unlocked manually by the administrator.
This parameter sets the **lockoutDuration** property of a password policy object.
The LDAP display name (**ldapDisplayName**) of this property is msDS-LockoutDuration.

The lockout duration must be greater than or equal to the lockout observation time for a password policy.
Use the *LockOutObservationWindow* parameter to set the lockout observation time.

Specify the lockout duration time interval in the following format:

`D.H:M:S.F`

where:
- D = Days (0 to 10675199)
- H = Hours (0 to 23)
- M = Minutes (0 to 59)
- S = Seconds (0 to 59)
- F= Fractions of a second (0 to 9999999)

```yaml
Type: TimeSpan
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -LockoutObservationWindow
Specifies the maximum time interval between two unsuccessful login attempts before the number of unsuccessful login attempts is reset to 0.
An account is locked when the number of unsuccessful login attempts exceeds the password policy lockout threshold.
This parameter sets the **lockoutObservationWindow** property of a password policy object.
The LDAP display name (**ldapDisplayName**) of this property is **msDS-lockoutObservationWindow**.

The lockout observation window must be smaller than or equal to the lockout duration for a password policy.
Use the *LockoutDuration* parameter to set the lockout duration time.

> [!NOTE]
> Setting the lockout observation window to 0 effectively means that the window is too short to
> observe more than one password attempt, therefore the account will never be locked out.

Specify the time interval in the following format:

`D:H:M:S.F`

where:
- D = Days (0 to 10675199)
- H = Hours (0 to 23)
- M = Minutes (0 to 59)
- S = Seconds (0 to 59)
- F= Fractions of a second (0 to 9999999)

Note: Time values must be between the following values: 0:0:0:0.0 and 10675199:02:48:05.4775807.

```yaml
Type: TimeSpan
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -LockoutThreshold
Specifies the number of unsuccessful login attempts that are permitted before an account is locked out.
This number increases when the time between unsuccessful login attempts is less than the time specified for the lockout observation time window.
This parameter sets the **LockoutThreshold** property of a password policy.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MaxPasswordAge
Specifies the maximum length of time that you can have the same password.
After this time period, the password expires and you must create a new one.

This parameter sets the **maxPasswordAge** property of a password policy.
The LDAP display name (**ldapDisplayName**) for this property is maxPwdAge.

Specify the time interval in the following format:

`D.H:M:S.F`

where:
- D = Days (0 to 10675199)
- H = Hours (0 to 23)
- M = Minutes (0 to 59)
- S = Seconds (0 to 59)
- F= Fractions of a second (0 to 9999999)

Note: Time values must be between the following values: 0 and 10675199:02:48:05.4775807.

```yaml
Type: TimeSpan
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MinPasswordAge
Specifies the minimum length of time before you can change a password.

This parameter sets the **minPasswordAge** property of a password policy.
The LDAP display name (**ldapDisplayName**) for this property is minPwdAge.

Specify the time interval in the following format:

`D.H:M:S.F`

where:
- D = Days (0 to 10675199)
- H = Hours (0 to 23)
- M = Minutes (0 to 59)
- S = Seconds (0 to 59)
- F= Fractions of a second (0 to 9999999)

Note: Time values must be between the following values: 0 and 10675199:02:48:05.

```yaml
Type: TimeSpan
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MinPasswordLength
Specifies the minimum number of characters that a password must contain.
This parameter sets the **MinPasswordLength** property of the password policy.

```yaml
Type: Int32
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
This parameter sets the **Name** property of the Active Directory object.
The LDAP display name (**ldapDisplayName**) of this property is name.

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

### -OtherAttributes
Specifies object attribute values for attributes that are not represented by cmdlet parameters.
You can set one or more parameters at the same time with this parameter.
If an attribute takes more than one value, you can assign multiple values.
To identify an attribute, specify the LDAPDisplayName (**ldapDisplayName**) defined for it in the Active Directory schema.

Syntax:

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

### -PasswordHistoryCount
Specifies the number of previous passwords to save.
A user cannot reuse a password in the list of saved passwords.
This parameter sets the **PasswordHistoryCount** property for a password policy.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
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

### -ReversibleEncryptionEnabled
Specifies whether the directory must store passwords using reversible encryption.
This parameter sets the **ReversibleEncryption** property for a password policy.
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
Specifies the Active Directory Domain Services instance to connect to, by providing one of the following values for a corresponding domain name or directory server.
The service may be any of the following:  Active Directory Lightweight Domain Services, Active Directory Domain Services, or Active Directory snapshot instance.

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
A fine-grained password policy object that is a template for the new fine-grained password policy object is received by the *Instance* parameter.

## OUTPUTS

### None or Microsoft.ActiveDirectory.Management.ADFineGrainedPasswordPolicy
This cmdlet returns the new fine-grained password policy object when the *PassThru* parameter is specified.
By default, this cmdlet does not generate any output.

## NOTES
* This cmdlet does not work with Active Directory Lightweight Directory Services (AD LDS).
* This cmdlet does not work with a read-only domain controller.
* This cmdlet does not work with an Active Directory snapshot.

## RELATED LINKS

[Get-ADFineGrainedPasswordPolicy](./Get-ADFineGrainedPasswordPolicy.md)

[Remove-ADFineGrainedPasswordPolicy](./Remove-ADFineGrainedPasswordPolicy.md)

[Set-ADFineGrainedPasswordPolicy](./Set-ADFineGrainedPasswordPolicy.md)

[AD DS Administration Cmdlets in Windows PowerShell](./activedirectory.md)

